# EX 45 C program that implements a queue using an array, and performs insertion (enqueue) and display operations.
## DATE:
## AIM:
To write a C program that implements a queue using an array, and performs insertion (enqueue) and display operations. 

## Algorithm
1. Start. 
2. Define a variables. 
3. Write a functions to perform enqueue,dequeue ,display,peek in Queue using array. 
4. Read the value using scanf. 
5. Ask the user to make an input. 
6. Print out the answer. 
7. End

## Program:
```
#include <stdio.h>
#define SIZE 100

// Global variables for the queue
int queue[SIZE];
int front = -1, rear = -1;

// Function to insert an element into the queue
void enqueue(int value) {
    if (rear == SIZE - 1) {
        printf("Queue Overflow! Cannot insert %d\n", value);
        return;
    }
    if (front == -1) front = 0;  // Set front on first insertion
    rear++;
    queue[rear] = value;
    printf("Inserted %d into the queue.\n", value);
}

// Function to display the elements of the queue
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Queue elements are: ");
    for (int i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");
}

// Main function with a simple menu
int main() {
    int choice, value;

    while (1) {
        printf("\n--- Queue Menu ---\n");
        printf("1. Enqueue\n");
        printf("2. Display\n");
        printf("3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                display();
                break;
            case 3:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice! Try again.\n");
        }
    }

    return 0;
}

```

## Output:
1. Enqueue\
2. Display\
3. Exit\
Enter your choice: 2\
Queue elements are: 10 20 30 

## Result:
Thus the program was executed and the output was verified successfully.
