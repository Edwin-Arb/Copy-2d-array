#include <iostream>
using namespace std;

void FillArray(int* const arr, int const size)
{
	for (int i = 0; i < size; i++)
	{
		arr[i] = rand() % 10;
	}
}
void ShowArray(const int* const arr, int const size)
{
	for (int i = 0; i < size; i++)
	{
		cout << arr[i] << "\t";
	}
	cout << endl;
}
void main()
{
	int size = 10;
	int* firstArray = new int[size];
	int* secondArray = new int[size];

	FillArray(firstArray, size);
	FillArray(secondArray, size);

	cout << "FirstArray = \t";
	ShowArray(firstArray, size);
	cout << "SecondArray = \t";
	ShowArray(secondArray, size);

	delete[] firstArray;

	firstArray = new int[size];
	for (int i = 0; i < size; i++)
	{
		firstArray[i] = secondArray[i];
	}

	cout << "================================" << endl;

	cout << "FirstArray = \t";
	ShowArray(firstArray, size);
	cout << "SecondArray = \t";
	ShowArray(secondArray, size);

	delete[] firstArray;
	delete[] secondArray;
}
