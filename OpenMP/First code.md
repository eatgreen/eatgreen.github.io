#include "omp.h"
#include <stdio.h>
#include <iostream>

static long num_steps=100000;
double step;

int main()
{
	int num_threads=omp_get_max_threads();

	int i;
	double x,pi,*sum;

	sum=new double [num_threads];

	for(i=0; i<num_threads; i++)
	{
		sum[i]=0.0;
	}

	step=1.0/(double)num_steps;

#pragma omp parallel
	{
		int ID=omp_get_thread_num();
		
		#pragma omp for private(x)   //It is important to make x private to each thread.
		for(i=0; i<num_steps; i++)
		{
			x=(i+0.5)*step;
			sum[ID]=sum[ID]+4.0/(1.0+x*x);
		}
	}

	for(i=0; i<num_threads; i++)
	{
		pi+=step*sum[i];
	}

	printf("pi=%f",pi);
		
	return 0;
}