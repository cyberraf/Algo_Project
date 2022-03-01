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

      ---Carl: you can copy this else if part to paste into the main code directly
      
//EXCHANGE SORT
        else if (typeSort == 3)
        {

            gettimeofday(&startTime, NULL);

            //Exchange Sort
            exchangeSort(array, numNums);

            gettimeofday(&stopTime, NULL);


            start = startTime.tv_sec + (startTime.tc_usec / 1000000.0);
            stop = stopTime.tv_sec + (stopTime.tv_usec / 1000000.0);


            diff = stop - start;

            //Output of exchange sort
            cout << "Exchange Sort Results: " << endl;

            cout << "n = " << numNums << ", sort = 3 (exchange sort), " << "if frequency = " << i_cnt << ", elements moved = " << m_cnt << endl;
            cout << "time = " << setprecision(10) << diff << " seconds " << endl;

            outputArray(array, numNums);
         }
else if (typeSort == 4)
        {

            gettimeofday(&startTime, NULL);

            //Exchange Sort
            exchangeSort(array, numNums);

            gettimeofday(&stopTime, NULL);


            start = startTime.tv_sec + (startTime.tc_usec / 1000000.0);
            stop = stopTime.tv_sec + (stopTime.tv_usec / 1000000.0);


            diff = stop - start;

            //Output of exchange sort
            cout << "Quick Sort Results: " << endl;

            cout << "n = " << numNums << ", sort = 4 (quick sort), " << "if frequency = " << i_cnt << ", elements moved = " << m_cnt << ", number of quicksort calls: " << q_count << ", number of partition calls: " << p_cnt << endl;
            cout << "time = " << setprecision(10) << diff << " seconds " << endl;

            outputArray(array, numNums);
         }
      
      
      
      
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
      
      
      

long q_cnt = 0;  // used to count the number of times quicksort is called
long p_cnt = 0; //used to count the number of times partition is called

      
      
//Quick Sort function

void quickSort(int array[],int low, int high, int numNums)
{

        int pivotpoint;
        q_cnt++; // counts the number of calls of quick sort

        if (high > low)
        {
                partition(low, high, pivotpoint);
                p_cnt++; //counts of the number of partition calls

                quickSort(low, pivotpoint - 1);
                q_cnt++; // counts the number of calls of quickSort

                quickSort(pivotpoint + 1, high);
                q_cnt++; // counts the number of calls of quickSort

        }// end if statement


}// end quick sort
      
      
 void partition(int low, int high, int &pivotpoint)
{
        int i, i;

        int pivotitem, temp;

        pivotitem = array[low];

        j = low;

        for (i = low + 1; i <= high; ++)
        {
                i_cnt++; // counts number of if
                if (array[i] < pivotitem)
                {
                        j++;

                        //Exchange array[i] and array[j]
                        temp = array[i];
                        array[i] = array[j];
                        m_cnt++;

                        array[j] = temp;
                        m_cnt++;

                }//end if statement

                //Exchange array[low] and array[pivotpoint]
                pivotpoint = j;
                pivotitem = array[low];
                m_cnt++;

                array[low] = array[pivotpoint];
                m_cnt++;

        }// end for loop

}// end partition

 
      
      
      
