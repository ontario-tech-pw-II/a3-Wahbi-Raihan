## Reverse File program

Learning outcomes highlights: 
- dynamic memory allocation
- file operations
- array of pointers

**Problem:** Write a program to get two file names as command-line arguments. The input file has one string in each line (without space). The program writes the input file strings in the output file in a reverse order. The program can be used as follows: 

./rev_file infile.txt outfile.txt (create outfile.txt)

The starter code is written for you. You just need to insert your code as instructed.


```C++
#include <iostream>
#include <fstream>
#include <cstring>

using namespace std;

void freadnames(ifstream &, char * []);
void fwritenames_reverse(ofstream &,char * []);
void freenames(char * []);


int main(int argc, char *argv[])
{
	char *list[100];
    
    if(argc != 3){
    	cerr << "Number of argument is not correct!" << endl;
    	return 1;
    }

	ifstream fin(argv[1]);
	if(fin.fail()){
		cerr << "Cannot open the input file!" << endl;
		return 1;
	}

	ofstream fout(argv[2]);
	if(fin.fail()){
		cerr << "Cannot open the output file!" << endl;
		return 1;
	}

	freadnames(fin,list);
	fwritenames_reverse(fout,list);
	freenames(list);
	
	fin.close();
	fout.close();
	
	return 0; 
}

void freadnames(ifstream &f,char *list [])
{
	char x[200];

	int i = 0;

	// write a while loop to read one string form the input file and put it in x till the end file
		// inside the loop allocate the dynamic array for list[i]
		// copy string stored in x to list[i] array using strcpy
		// increment i 

	list[i] = nullptr;  // IMPORTANT: we put the null to the last pointer in list to mark the last element in list
}
void fwritenames_reverse(ofstream &f,char *list [])
{
	int i;
	for(i = 0; list[i] != nullptr ; ++i)
		;

	for(int j = i-1; j >= 0 ; --j)
	{
		// your code is here
	}
}
void freenames(char *list [])
{
	for (int i = 0; list[i] != nullptr; ++i)
	{
		delete [] list[i];;
	}
}
```
