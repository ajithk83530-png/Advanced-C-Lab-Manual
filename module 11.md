

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
```
#include <stdio.h>
int max_of_four(int a, int b, int c, int d)
{
    int max=a;
    if(b>max)
    {
        max=b;
    }
    else if(c>max)
    {
        max=c;
    }
    else if(d>max)
    {
        max=d;
    }
    return max;
}
int main()
{
    int a,b,c,d;
    scanf("%d%d%d%d",&a,&b,&c,&d);
    printf("%d",max_of_four(a,b,c,d));
    return 0;
}
```

Output:
<img width="330" height="330" alt="image" src="https://github.com/user-attachments/assets/f6263143-0c44-483a-b579-0e81f2c7f1f2" />


Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
```
#include <stdio.h>
void calculate_the_maximum(int n,int k)
{
    int max_and=0,max_or=0,max_xor=0;
    for(int i=1;i<=n;i++)
    {
        for(int j=i+1;j<=n;j++)
        {
            int and_res=i&j;
            int or_res=i|j;
            int xor_res=i^j;
            
            if(and_res<k && and_res>max_and)
            {
                max_and=and_res;
            }
            if(or_res<k && or_res>max_or)
            {
                max_or=or_res;
            }
            if(xor_res<k && xor_res>max_xor)
            {
                max_xor=xor_res;
            }
        }
        
    }
    printf("%d\n%d\n%d",max_and,max_or,max_xor);
}
int main()
{
    int n,k;
    scanf("%d%d",&n,&k);
    calculate_the_maximum(n,k);
    return 0;
}
```
Output:
<img width="330" height="376" alt="image" src="https://github.com/user-attachments/assets/36b87d71-7fff-42a8-bb24-f860e93eb6a8" />


Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
```
#include<stdio.h>
#define MAX_BOOKS_PER_SHELF 100
int main()
{
    int n,m;
    scanf("%d%d",&n,&m);
    int shelfs[n][100];
    int shelf_size[n];
    for(int i=0;i<n;i++)
    {
        shelf_size[i]=0;
    }
    for(int i=0;i<m;i++)
    {
        int query;
        scanf("%d",&query);
        if(query==1)
        {
            int x,y;
            scanf("%d%d",&x,&y);
            shelfs[x][shelf_size[x]]=y;
            shelf_size[x]++;
        }
        else if(query==2)
        {
            int x,y;
            scanf("%d%d",&x,&y);
            printf("%d\n",shelfs[x][y]);
        }
        else if (query==3)
        {
            int x;
            scanf("%d",&x);
            printf("%d\n",shelf_size[x]);
        }
    }
    return 0;
}
```
Output:
<img width="335" height="267" alt="image" src="https://github.com/user-attachments/assets/5c6a6055-bd83-4584-bdb1-bec8e307aaf8" />



Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
```
#include<stdio.h>
int main()
{
    int n;
    scanf("%d",&n);
    int arr[n];
    int sum=0;
    for(int i=0;i<n;i++)
    {
        scanf("%d",&arr[i]);
        sum+=arr[i];
    }
    printf("%d",sum);
    
    
}
```

Output:
<img width="832" height="208" alt="image" src="https://github.com/user-attachments/assets/b26f9647-07ac-4618-8c80-56cf1f5e127d" />


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:
```
#include<stdio.h>
#include<string.h>
int main()
{
    char str[100];
    fgets(str,sizeof(str),stdin);
    int len=sizeof(str);
    int count=1;
     for(int i=0;i<len-1;i++){
         if(str[i]==' ')
         count++;
         
     }
     printf("Total number of words in the string is :%d",count);
    return 0;
}
```

Output:
<img width="827" height="116" alt="image" src="https://github.com/user-attachments/assets/b16a1b1c-63a6-49a7-a8ae-e3b700778af5" />


Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
