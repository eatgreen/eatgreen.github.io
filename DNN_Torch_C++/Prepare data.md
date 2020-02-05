# Prepare data
## Workflow
1. Construct datasets
		  
		  auto train_dataset0 = torch::data::datasets::MNIST(kDataRoot);
	
	Here *train_dataset0* has type **datasets**.

2. Do some mapping
		 
		 auto train_dataset=train_dataset0.map(torch::data::transforms::Normalize<>(0.1307, 0.3081))
		 .map(torch::data::transforms::Stack<>());
	Here *train_dataset* has type **MapDataset**. 
	
3. Make data loader

		  auto test_loader = torch::data::make_data_loader(std::move(test_dataset), kTestBatchSize);
  Here *test_loader* has type **std::unique_ptr<DataLoader>**.
  
Note that the template declaration of make_data_loader looks like 
		
		make_data_loader( Dataset dataset, DataLoaderOptions options, Sampler sampler)
	  
Or

	make_data_loader( Dataset dataset, DataLoaderOptions options = DataLoaderOptions())
	
In C++, we do not need to specify every template type. Certain type can be inferred through parameter type implicitly.

When call make_data_loader, 

 auto train_loader =
      torch::data::make_data_loader<torch::data::samplers::SequentialSampler>( std::move(train_dataset), kTrainBatchSize);
      
Calling the second constructor and kTrainBatchSize is used to construct the object DataLoaderOptions. 

## A side notes on keyword using in c++
For example in

		  template <typename Dataset, typename Sampler> 
		  class DataLoader {
		  public:
		  using Batch = typename Dataset::BatchType;

Dataset is the template parameter, the type BatchType is dependent on Dataset. Without the keyword typename, the compiler do not know *Dataset::BatchType* is a type name.