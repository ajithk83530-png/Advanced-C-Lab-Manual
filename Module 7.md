EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim: To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:

Declare structure eligible with age (integer) and n (character array)
Declare variable e of type eligible
Input age and name using scanf, store in e
If e.age <= 6
Print "Vaccine Eligibility: No" Else
Print "Vaccine Eligibility: Yes"
Print details (e.age, e.n)
Return 0
Program:
```
#include <stdio.h>

struct Person
{
    char name[50];
    int age;
};

int main()
{
    int n, i;

    printf("Enter the number of persons: ");
    scanf("%d", &n);

    struct Person p[n];

    // Input details
    for(i = 0; i < n; i++)
    {
        printf("\nEnter name of person %d: ", i + 1);
        scanf("%s", p[i].name);

        printf("Enter age: ");
        scanf("%d", &p[i].age);
    }

    // Check eligibility
    printf("\nVaccine Eligibility:\n");
    for(i = 0; i < n; i++)
    {
        if(p[i].age > 6)
            printf("%s (Age %d) - Eligible for Vaccine\n", p[i].name, p[i].age);
        else
            printf("%s (Age %d) - Not Eligible for Vaccine\n", p[i].name, p[i].age);
    }

    return 0;
}
```

Output:
```
Enter the number of persons: 3

Enter name of person 1: Arun
Enter age: 5

Enter name of person 2: Priya
Enter age: 8

Enter name of person 3: Ravi
Enter age: 12
```


Result: Thus, the program is verified successfully.

EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION Aim: To write a C program for passing structure as function and returning a structure from a function

Algorithm:

Define structure numbers with members a and b.
Declare variable n of type numbers.
Prompt the user to enter values for a and b.
Input values for a and b into n using scanf.
Call the add function with n as an argument.
Print the result returned by the add function.
Return 0
Program:

```
#include <stdio.h>

// Define structure
struct Student
{
    int rollNo;
    char name[50];
    float marks;
};

// Function to receive structure as argument
void display(struct Student s)
{
    printf("\nStudent Details:\n");
    printf("Roll No : %d\n", s.rollNo);
    printf("Name    : %s\n", s.name);
    printf("Marks   : %.2f\n", s.marks);
}

// Function to return structure
struct Student updateMarks(struct Student s)
{
    s.marks = s.marks + 5;   // Add grace marks
    return s;
}

int main()
{
    struct Student s1;

    // Input
    printf("Enter Roll Number: ");
    scanf("%d", &s1.rollNo);

    printf("Enter Name: ");
    scanf("%s", s1.name);

    printf("Enter Marks: ");
    scanf("%f", &s1.marks);

    // Pass structure as function argument
    display(s1);

    // Return structure from function
    s1 = updateMarks(s1);

    printf("\nAfter Adding Grace Marks:\n");
    display(s1);

    return 0;
}
```

Output:
```
Enter Roll Number: 101
Enter Name: Aancy
Enter Marks: 85

Student Details:
Roll No : 101
Name    : Aancy
Marks   : 85.00

After Adding Grace Marks:

Student Details:
Roll No : 101
Name    : Aancy
Marks   : 90.00
```

Result: Thus, the program is verified successfully

EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim: To write a C program to read a file name from user

Algorithm:

Include the necessary header file stdio.h.
Begin the main function.
Declare a file pointer p. Declare a character array name to store the file name.
Prompt the user to enter a file name. Use scanf to input the file name into the name array.
Print a message indicating that the file with the specified name has been created successfully.
Use fopen to open a file with the name provided by the user in write mode ("w").
If successful, continue to the next step.
If unsuccessful, print an error message and exit the program with a non-zero status.
Print a message indicating that the file has been opened successfully.
Use fclose to close the file.
Print a message indicating that the file has been closed.
End the main function.
Return 0 to indicate successful program execution.
Program:
```
#include <stdio.h>

int main()
{
    FILE *fp;
    char filename[100], text[200];

    // Read file name
    printf("Enter file name: ");
    scanf("%s", filename);

    // Open file in write mode
    fp = fopen(filename, "w");

    if (fp == NULL)
    {
        printf("Error opening file!\n");
        return 1;
    }

    // Read text from user
    printf("Enter text to write into the file:\n");
    getchar();   // Clear newline from input buffer
    fgets(text, sizeof(text), stdin);

    // Write text to file
    fputs(text, fp);

    // Close file
    fclose(fp);

    printf("Data written successfully to %s\n", filename);

    return 0;
}
```

Output:

```

Enter file name: sample.txt
Enter text to write into the file:
Welcome to File Handling in C.
Data written successfully to sample.txt
```

Result: Thus, the program is verified successfully

EXP NO:4 PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE Aim: To write a C program to read, a file and insert text in that file Algorithm:

Include the necessary header file stdio.h.
Begin the main function.
Declare a file pointer p. Declare character arrays name and text. Declare an integer variable num.
Prompt the user to enter a file name and the number of strings. Use scanf to input the file name into the name array and the number of strings into the num variable.
Use fopen to open a file with the name provided by the user in write mode ("w").
If successful, continue to the next step.
If unsuccessful, print an error message and exit the program with a non-zero status.
Print a message indicating that the file has been opened successfully.
Use a loop to input strings from the user and write them to the file using fputs.
Use fclose to close the file.
Print a message indicating that data has been added successfully.
End the main function.
Return 0 to indicate successful program execution.
Program:
```
#include <stdio.h>

int main()
{
    FILE *fp;
    char filename[100];
    char text[200], insertText[200];

    printf("Enter file name: ");
    scanf("%s", filename);
    getchar();

    fp = fopen(filename, "w");

    if (fp == NULL)
    {
        printf("Unable to open file.\n");
        return 1;
    }

    printf("Enter text to write:\n");
    fgets(text, sizeof(text), stdin);

    fputs(text, fp);
    fclose(fp);

    fp = fopen(filename, "a");

    if (fp == NULL)
    {
        printf("Unable to open file.\n");
        return 1;
    }

    printf("Enter text to insert (append):\n");
    fgets(insertText, sizeof(insertText), stdin);

    fputs(insertText, fp);

    fclose(fp);

    printf("Text written and inserted successfully.\n");

    return 0;
}
```

Output:
```
Enter file name: sample.txt
Enter text to write:
Hello, World!
Enter text to insert (append):
Welcome to File Handling.
Text written and inserted successfully.
```

Result: Thus, the program is verified successfully

Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim: The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm: 1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:
```
#include <stdio.h>

struct Student
{
    int rollNo;
    char name[50];
    int age;
    float marks;
};

int main()
{
    struct Student s;

    printf("Enter Roll Number: ");
    scanf("%d", &s.rollNo);

    printf("Enter Name: ");
    scanf("%s", s.name);

    printf("Enter Age: ");
    scanf("%d", &s.age);

    printf("Enter Marks: ");
    scanf("%f", &s.marks);

    printf("\n----- Student Details -----\n");
    printf("Roll Number : %d\n", s.rollNo);
    printf("Name        : %s\n", s.name);
    printf("Age         : %d\n", s.age);
    printf("Marks       : %.2f\n", s.marks);

    return 0;
}
```
Output:
```
Enter Roll Number: 101
Enter Name: Aancy
Enter Age: 19
Enter Marks: 92.5

----- Student Details -----
Roll Number : 101
Name        : Aancy
Age         : 19
Marks       : 92.50
```

Result: Thus, the program is verified successfully
