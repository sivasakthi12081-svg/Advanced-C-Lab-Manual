EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
```
#include <stdio.h>
struct eligible{
    char n[30];
    int age;
};
int main(){
    struct eligible e[10];
    int i, num;
    printf("Enter the number of persons: ");
    scanf("%d", &num);
    for(i = 0; i < num; i++){
        printf("\nEnter Name: ");
        scanf("%s", e[i].n);
        printf("Enter Age: ");
        scanf("%d", &e[i].age);
    }
    printf("\n--- Vaccine Eligibility ---\n");
    for(i = 0; i < num; i++){
        printf("\nName : %s", e[i].n);
        printf("\nAge  : %d", e[i].age);
        if(e[i].age <= 6)
            printf("\nVaccine Eligibility: No\n");
        else
            printf("\nVaccine Eligibility: Yes\n");
    }
    return 0;
}
```
Output:
<img width="959" height="502" alt="Screenshot 2026-09-07 172241" src="https://github.com/user-attachments/assets/9dcb4df5-9445-4d9c-834a-0c811f25613b" />


Result:
Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:
```
#include <stdio.h>
struct numbers{
    int a, b, sum;
};
struct numbers add(struct numbers n){
    n.sum = n.a + n.b;
    return n;
}
int main(){
    struct numbers n;
    printf("Enter first number: ");
    scanf("%d", &n.a);
    printf("Enter second number: ");
    scanf("%d", &n.b);
    n = add(n);
    printf("\nFirst Number  : %d", n.a);
    printf("\nSecond Number : %d", n.b);
    printf("\nSum           : %d", n.sum);
    return 0;
}
```
Output:
<img width="959" height="499" alt="Screenshot 2026-09-07 172535" src="https://github.com/user-attachments/assets/bd2c895f-0da8-498b-8937-c0d6a3a3b82c" />


Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

```
#include <stdio.h>
int main(){
    FILE *p;
    char name[50];
    printf("Enter the file name: ");
    scanf("%s", name);
    p = fopen(name, "w");
    if (p == NULL){
        printf("Error in creating/opening the file.\n");
        return 1;
    }
    printf("File '%s' created and opened successfully.\n", name);
    fclose(p);
    printf("File closed successfully.\n");
    return 0;
}
```
Output:
<img width="959" height="496" alt="Screenshot 2026-09-07 173510" src="https://github.com/user-attachments/assets/c4f268c4-ff44-424a-a246-5b6fb011cf04" />

Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```
#include <stdio.h>
int main(){
    FILE *p;
    char name[50], text[100];
    int num, i;
    printf("Enter the file name: ");
    scanf("%s", name);
    printf("Enter the number of strings: ");
    scanf("%d", &num);
    p = fopen(name, "w");
    if (p == NULL){
        printf("Error in opening the file.\n");
        return 1;
    }
    printf("File opened successfully.\n");
    getchar(); 
    for(i = 0; i < num; i++){
        printf("Enter string %d: ", i + 1);
        fgets(text, sizeof(text), stdin);
        fputs(text, p);
    }
    fclose(p);
    printf("Data added successfully.\n");
    return 0;
}
```
Output:
<img width="959" height="488" alt="Screenshot 2026-09-07 173830" src="https://github.com/user-attachments/assets/dcce77d9-0f95-425c-9682-a04b16242a3d" />


Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

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
#include <stdlib.h>
struct student{
    char name[30];
    int marks;
};
int main(){
    struct student *s;
    int n, i;
    printf("Enter the number of subjects: ");
    scanf("%d", &n);
    s = (struct student *)malloc(n * sizeof(struct student));
    if (s == NULL){
        printf("Memory allocation failed.\n");
        return 1;
    }
    for (i = 0; i < n; i++){
        printf("\nEnter subject %d name: ", i + 1);
        scanf("%s", s[i].name);
        printf("Enter marks: ");
        scanf("%d", &s[i].marks);
    }
    printf("\n--- Student Details ---\n");
    for (i = 0; i < n; i++){
        printf("\nSubject Name: %s", s[i].name);
        printf("\nMarks: %d\n", s[i].marks);
    }
    free(s);
    return 0;
}
```
Output:
<img width="479" height="461" alt="Screenshot 2026-09-07 174347" src="https://github.com/user-attachments/assets/6df6fece-811d-42c2-912e-dcd998684f29" />
<img width="480" height="206" alt="Screenshot 2026-09-07 174402" src="https://github.com/user-attachments/assets/c1630e4d-c451-4438-9dad-88e232e23b86" />

Result:
Thus, the program is verified successfully
