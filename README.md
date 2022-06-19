# Banker-Algoritm
Prepared By : 

| NAME  | MATRIC NO. |
| ------------- | ------------- |
| Nor Zuhayra Amalin   | 2011642  |
| Wan Nurshafiqah Nabila Binti Wan Masri   | 2013674  |
| Faridah Ilyana Binti Ahmad Shariffuddin  | 2022144  |

*Lecturer Dr. Rizal Bin Mohd. Nor*


# CONTENT
1. [Q1](https://github.com/ilyana-8/Banker-Algorithm/blob/main/README.md#Q1)
2. [Q2](https://github.com/ilyana-8/Banker-Algorithm/blob/main/README.md#Q2)
3. [Q3](https://github.com/ilyana-8/Banker-Algorithm/blob/main/README.md#Q3)
4. [Q4](https://github.com/ilyana-8/Banker-Algorithm/blob/main/README.md#Q4)
5. [Q5](https://github.com/ilyana-8/Banker-Algorithm/blob/main/README.md#Q5)


# Q1
// No 1 : Implement Banker Algorithm
#include <stdio.h>
int main()
{
int p = 5, r = 3, i, j, k;


# Q2
//No 2 : Input
int available[3] = { 10, 5, 7 };

int allocation[5][3] = { { 7, 5, 3 },
                         { 3, 2, 2 },
                         { 9, 0, 2 },
                         { 2, 2, 2 },
                         { 4, 3, 3} };
                         
int max[5][3] = { { 0, 1, 0 },
                { 2, 0, 0 },
                { 3, 0, 2 },
                { 2, 1, 1 },
                { 0, 0, 2 } };
                
int f[p], ans[p], ind = 0;
for (k = 0; k < p; k++) {
     f[k] = 0;
    }
int need[p][r];
for (i = 0; i < p; i++) {
     for (j = 0; j < r; j++) 
	 need[i][j] = max[i][j] - allocation[i][j];
    }  
int y = 0;
for (k = 0; k < 5; k++) {
     for (i = 0; i < p; i++) {
     if (f[i] == 0) {
     int flag = 0;
         for (j = 0; j < r; j++) {
             if (need[i][j] > available[j]){ flag = 1; 
			 break;
                 } 
            }
			if (flag == 0) { ans[ind++] = i;
                for (y = 0; y < r; y++) 
                     available[y] += allocation[i][y];
                     f[i] = 1;
                } 
        }
        }
    }
    
    
# Q3
// No 3 : Safe State
printf("Safe Sequence for the process is : \n");
for (i = 0; i < p - 1; i++) 
	printf(" Thread %d ->", ans[i]); 
	printf(" Thread %d", ans[p - 1]);
}

# Q4
The banker will grant a request if it satisfies the safety algorithm outlined in Section 8.6.3.1. If a request does not leave the system in a safe state, the banker will deny it. The request function should return 0 if successful and –1 if unsuccessful. Demonstrate an order in which the threads may complete for successful request.  

