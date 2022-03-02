# Algo_Project

      ---Carl: you can copy this else if part to paste into the main code directly
      
//EXCHANGE SORT

---------------------- Code for choosing Exchange Sort --------------------------------------------

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
         
---------------------  End Code for choosing Exchange Sort --------------------------------------------




--------------------  Code for Chossing  Quick Sort -----------------------------------------------------

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
      
--------------------------------- End Code for Choosing Quick Sort -------------------------------------------------



-------------------------------- Code for Exchange Sort  function ---------------------------------------------
      
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
      
------------------------------ End Code for Exchange Sort function --------------------------------------------------------------



------------------------------ Code for Quick Sort Function -------------------------------------------------------------------

long i_cnt = 0;  // used to count the number of times an "if" statement is executed
long m_cnt = 0;  // used to count the number of times an element is moved somewhere
long q_cnt = 0;  // used to count the number of times quicksort is called
long p_cnt = 0; //used to count the number of times partition is called


//Quick Sort function

void quickSort(int array[],int low, int high, int numNums)
{

        int pivotpoint;
        q_cnt++; // counts the number of calls of quick sort

        if (high > low)
        {
                partition(array, low, high, pivotpoint);
                p_cnt++; //counts of the number of partition calls

                quickSort(array, low, pivotpoint - 1, numNums);
                q_cnt++; // counts the number of calls of quickSort

                quickSort(array, pivotpoint + 1, high, numNums);
                q_cnt++; // counts the number of calls of quickSort

        }// end if statement


}// end quick sort
      
-------------------------- End Code for Quick Sort ----------------------------------------------------------------------



------------------------- Code for Partition --------------------------------------------------------------------------

void partition(int array[], int low, int high, int& pivotpoint)
{
        int i, j;

        int pivotitem;
        int  temp;

        pivotitem = array[low];

        j = low;

        for (i = low + 1; i <= high; i++)
        {
                i_cnt++; // counts number of if
                if (array[i] < pivotitem)
                {
                        j++;

                        //Exchange array[i] and array[j]
                        temp = array[i];
                        array[i] = array[j];
                        m_cnt++;//increment count for moved item

                        array[j] = temp;
                        m_cnt++;//increment count for moved item

                }//end if statement

                //Exchange array[low] and array[pivotpoint]
                pivotpoint = j;
                pivotitem = array[low];
                m_cnt++;//increment count for moved item

                array[low] = array[pivotpoint];
                m_cnt++;//increment count for moved item

        }// end for loop

}// end partition
      
------------------------------ End Code for  Partition function ----------------------------------------
