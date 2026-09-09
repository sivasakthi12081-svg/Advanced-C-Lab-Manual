

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void display()
{
    struct Node *p = head;

    if (p == NULL)
    {
        printf("Stack is empty");
        return;
    }

    printf("Stack elements are:\n");

    while (p != NULL)
    {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main()
{
    struct Node *n1, *n2, *n3;

    n1 = (struct Node *)malloc(sizeof(struct Node));
    n2 = (struct Node *)malloc(sizeof(struct Node));
    n3 = (struct Node *)malloc(sizeof(struct Node));

    n1->data = 30;
    n1->next = n2;

    n2->data = 20;
    n2->next = n3;

    n3->data = 10;
    n3->next = NULL;

    head = n1;

    display();

    return 0;
}
```

Output:

<img width="477" height="242" alt="Screenshot 2026-09-10 000118" src="https://github.com/user-attachments/assets/70d3d33d-ae46-4226-8803-5b54d2c8f1bc" />



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void pop()
{
    struct Node *temp;

    if (head == NULL)
    {
        printf("Stack is empty.\n");
        return;
    }

    temp = head;
    printf("Popped element: %d\n", head->data);
    head = head->next;
    free(temp);
}

int main()
{
    struct Node *n1, *n2, *n3;

    n1 = (struct Node *)malloc(sizeof(struct Node));
    n2 = (struct Node *)malloc(sizeof(struct Node));
    n3 = (struct Node *)malloc(sizeof(struct Node));

    n1->data = 30;
    n1->next = n2;

    n2->data = 20;
    n2->next = n3;

    n3->data = 10;
    n3->next = NULL;

    head = n1;

    pop();

    return 0;
}
```

Output:

<img width="481" height="260" alt="Screenshot 2026-09-10 000159" src="https://github.com/user-attachments/assets/5f35ae0a-1b7e-471b-a547-6c30e0d738f9" />




Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void display()
{
    struct Node *p = front;

    if (front == NULL)
    {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements are:\n");

    while (p != NULL)
    {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main()
{
    struct Node *n1, *n2, *n3;

    n1 = (struct Node *)malloc(sizeof(struct Node));
    n2 = (struct Node *)malloc(sizeof(struct Node));
    n3 = (struct Node *)malloc(sizeof(struct Node));

    n1->data = 10;
    n1->next = n2;

    n2->data = 20;
    n2->next = n3;

    n3->data = 30;
    n3->next = NULL;

    front = n1;
    rear = n3;

    display();

    return 0;
}
```

Output:

<img width="479" height="256" alt="Screenshot 2026-09-10 000239" src="https://github.com/user-attachments/assets/14b3bc83-5414-4c0e-ab15-70545ab5b642" />


Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value)
{
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if (front == NULL)
    {
        front = p;
        rear = p;
    }
    else
    {
        rear->next = p;
        rear = p;
    }
}

void display()
{
    struct Node *p = front;

    printf("Queue elements are:\n");

    while (p != NULL)
    {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main()
{
    enqueue(10);
    enqueue(20);
    enqueue(30);

    display();

    return 0;
}
```

Output:

<img width="482" height="251" alt="Screenshot 2026-09-10 000341" src="https://github.com/user-attachments/assets/4cf40374-c77e-43ff-838e-908aeac30442" />


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void peek()
{
    if (front == NULL)
    {
        printf("Queue is empty.\n");
    }
    else
    {
        printf("Peek element: %d\n", front->data);
    }
}

int main()
{
    struct Node *n1, *n2, *n3;

    n1 = (struct Node *)malloc(sizeof(struct Node));
    n2 = (struct Node *)malloc(sizeof(struct Node));
    n3 = (struct Node *)malloc(sizeof(struct Node));

    n1->data = 10;
    n1->next = n2;

    n2->data = 20;
    n2->next = n3;

    n3->data = 30;
    n3->next = NULL;

    front = n1;
    rear = n3;

    peek();

    return 0;
}
```

Output:

<img width="481" height="217" alt="Screenshot 2026-09-10 000435" src="https://github.com/user-attachments/assets/253f0ffa-8b77-42be-8afb-ff9d291ca777" />

Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


