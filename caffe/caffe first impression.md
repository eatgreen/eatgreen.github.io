###cpp file main function
1. getting 
  * model file
  * trained file
  * mean file
  * label file
  * target file

2. class classfier
  * constructor
  * vector of type Prediction := pair<string, float>
  * shared_ptr<Net<float>> net_
  * in constructor, 
    net_.reset(new Net<floar>(model_file, TEST) )

  **in net , we load the net configuration file xxx.prototxt**