# Algo_Project
-------------- Rafik Working on this part -------

#include <iostream>
#include <fstream>

using namespace std;


int main()
{

   ifstream inFile;
   string filename;

   cout << "Enter the name of the dataset (almostS, randomS, reverseS, or duplicates): " << endl;
   cin >> filename;

   inFile.open(filename);

   if (inFile.fail())
   {
       cerr <<"No such file!" << endl;
       exit(1);
   }// end if statement

   int MAX  = 1000000;//1 TRILLION

   int numToSort;
   int array[MAX];

   cout << "Enter the number of randomnumbers to process (sort) <= 100,000: " << endl;
   cin >> numToSort;

   int algNum;

   cout <<"Enter the name of the algorithm you want to test:  ";
   cin >> algNum;
   cout << endl;

   //Load the data until numToSort
   for(int i = 0; i <= numToSort; i++)
       inFile >> array[i];

   inFile.close();

}//end of main
  
--------------------------------- END RAFIK PART ------------------------------------
