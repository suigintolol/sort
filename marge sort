#include "pch.h"
#include <iostream>

void Merge(int A[], int p, int q, int r)
{
	int left = 0;
	int right = 0;
	p--;
	q--;
	r--;
	int *arr = new int[r-p+1];
	for (size_t i = 0; i < r - p + 1; i++)
	{
		if (left == q-p+1)
		{
			arr[i] = A[q + 1+ right];
			right++;
		}
		else if (right == r-q)
		{
			arr[i] = A[p + left];
			left++;
		}
		else
		{
			if (A[p + left] < A[q + 1 + right])
			{
				arr[i] = A[p + left];
				left++;
			}
			else
			{
				arr[i] = A[q + 1 + right];					
				right++;
			}
		}
	}
	for (size_t i = 0; i < r - p + 1; i++)
	{
		A[p + i] = arr[i];
	}
	delete[]arr;
}

void Sort(int A[], int p, int r)
{	
	if (p < r)
	{	
		int q = ceil((p + r) / 2);
		Sort(A, p, q);
		Sort(A, q + 1, r);
		Merge(A, p, q, r);
	}
}

int main()
{
	int A[] = {5,2,4,6,1,3,2,6};
	Sort(A, 1, sizeof(A) / sizeof(A[0]));
	for (size_t i = 0; i < (sizeof(A) / sizeof(A[0])); i++)
	{
		std::cout << std::endl << A[i] << std::endl;
	}
	return 0;
}



