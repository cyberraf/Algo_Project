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

      
      
//exchangesort function
void exchangeSort(int array[], int numNums)
{
        int temp;// variable to hold the temporary value of the current array slot before it gets swapped with the next value

        for (int i = 0; i < numNums; i++)
        {
                for (int j = i + 1; j < numNums; j++)
                {
                        i_cnt++; //count number of ifs

                        if (array[j] < array[i])
                        {
                                //i_cnt++; //count number of ifs

                                temp = array[i];// holds the value of array[i] temporally

                                array[i] = array[j];
                                m_cnt++; // array[j] value is moved to array[i]

                                array[j] = temp;
                                m_cnt++;// temp value is moved to array[j]

                        }// end if statement

                }// end inner for loop

        }// end outer for loop

}// end exchange sort
