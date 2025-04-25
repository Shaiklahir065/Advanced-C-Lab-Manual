EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
```
#include <stdio.h>
#define MAX 5 
struct Stack {
    int arr[MAX];
    int top;
};
void initStack(struct Stack *s) {
    s->top = -1;  
}
int isFull(struct Stack *s) {
    return s->top == MAX - 1;
}
int isEmpty(struct Stack *s) {
    return s->top == -1;
}
void push(struct Stack *s, int value) {
    if (isFull(s)) {
        printf("Stack overflow! Cannot push %d\n", value);
    } else {
        s->arr[++(s->top)] = value;
        printf("%d pushed to stack\n", value);
    }
}
int pop(struct Stack *s) {
    if (isEmpty(s)) {
        printf("Stack underflow! No elements to pop\n");
        return -1; 
    } else {
        return s->arr[(s->top)--];
    }
}
void display(struct Stack *s) {
    if (isEmpty(s)) {
        printf("Stack is empty\n");
    } else {
        printf("Stack elements: ");
        for (int i = s->top; i >= 0; i--) {
            printf("%d ", s->arr[i]);
        }
        printf("\n");
    }
}
int main() {
    struct Stack stack; 
    initStack(&stack);  
    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);
    push(&stack, 40);
    push(&stack, 50);
    push(&stack, 60);
    display(&stack);
    printf("Popped element: %d\n", pop(&stack));
    printf("Popped element: %d\n", pop(&stack));
    display(&stack);
    return 0;
}
```
Output:
```
10 pushed to stack
20 pushed to stack
30 pushed to stack
40 pushed to stack
50 pushed to stack
Stack overflow! Cannot push 60
Stack elements: 50 40 30 20 10 
Popped element: 50
Popped element: 40
Stack elements: 30 20 10 
```


Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
```
#include <stdio.h>
#define MAX 5  
struct Stack {
    int arr[MAX];
    int top;
};
void initStack(struct Stack *s) {
    s->top = -1;  
}
int isFull(struct Stack *s) {
    return s->top == MAX - 1;
}
void push(struct Stack *s, int value) {
    if (isFull(s)) {
        printf("Stack overflow! Cannot push %d\n", value);
    } else {
        s->arr[++(s->top)] = value;
        printf("%d pushed to stack\n", value);
    }
}

int main() {
    struct Stack stack; 
    initStack(&stack);   
    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);
    push(&stack, 40);
    push(&stack, 50);
    push(&stack, 60);

    return 0;
}
```
Output:
```
10 pushed to stack
20 pushed to stack
30 pushed to stack
40 pushed to stack
50 pushed to stack
Stack overflow! Cannot push 60
```



Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
```
#include <stdio.h>
#define MAX 5 
struct Queue {
    int arr[MAX];
    int front, rear;
};
void initQueue(struct Queue *q) {
    q->front = -1;
    q->rear = -1;
}
int isFull(struct Queue *q) {
    return q->rear == MAX - 1;
}
int isEmpty(struct Queue *q) {
    return q->front == -1 || q->front > q->rear;
}
void enqueue(struct Queue *q, int value) {
    if (isFull(q)) {
        printf("Queue is full! Cannot enqueue %d\n", value);
    } else {
        if (q->front == -1) {
            q->front = 0;  
        }
        q->arr[++(q->rear)] = value;
        printf("%d enqueued to queue\n", value);
    }
}
int dequeue(struct Queue *q) {
    if (isEmpty(q)) {
        printf("Queue is empty! Cannot dequeue\n");
        return -1; 
    } else {
        int value = q->arr[q->front++];
        if (q->front > q->rear) {
            q->front = q->rear = -1; 
        }
        return value;
    }
}
void display(struct Queue *q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
    } else {
        printf("Queue elements: ");
        for (int i = q->front; i <= q->rear; i++) {
            printf("%d ", q->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Queue q; 
    initQueue(&q);  
    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);
    enqueue(&q, 40);
    enqueue(&q, 50);
    enqueue(&q, 60);
    display(&q);
    printf("Dequeued element: %d\n", dequeue(&q));
    printf("Dequeued element: %d\n", dequeue(&q));
    display(&q);

    return 0;
}
```
Output:
```
10 enqueued to queue
20 enqueued to queue
30 enqueued to queue
40 enqueued to queue
50 enqueued to queue
Queue is full! Cannot enqueue 60
Queue elements: 10 20 30 40 50 
Dequeued element: 10
Dequeued element: 20
Queue elements: 30 40 50 
```
Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:
```
#include <stdio.h>
#define MAX 5  
struct Queue {
    int arr[MAX];
    int front, rear;
};
void initQueue(struct Queue *q) {
    q->front = -1;
    q->rear = -1;
}
int isFull(struct Queue *q) {
    return q->rear == MAX - 1;
}
int isEmpty(struct Queue *q) {
    return q->front == -1 || q->front > q->rear;
}
void enqueue(struct Queue *q, int value) {
    if (isFull(q)) {
        printf("Queue is full! Cannot enqueue %d\n", value);
    } else {
        if (q->front == -1) {
            q->front = 0; 
        }
        q->arr[++(q->rear)] = value;
        printf("%d enqueued to queue\n", value);
    }
}
int main() {
    struct Queue q; 
    initQueue(&q); 
    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);
    enqueue(&q, 40);
    enqueue(&q, 50);
    enqueue(&q, 60);

    return 0;
}
```
Output:
```
10 enqueued to queue
20 enqueued to queue
30 enqueued to queue
40 enqueued to queue
50 enqueued to queue
Queue is full! Cannot enqueue 60
```
Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:
```
#include <stdio.h>
#define MAX 5 
struct Queue {
    int arr[MAX];
    int front, rear;
};
void initQueue(struct Queue *q) {
    q->front = -1;
    q->rear = -1;
}
int isFull(struct Queue *q) {
    return q->rear == MAX - 1;
}
int isEmpty(struct Queue *q) {
    return q->front == -1 || q->front > q->rear;
}
void enqueue(struct Queue *q, int value) {
    if (isFull(q)) {
        printf("Queue is full! Cannot enqueue %d\n", value);
    } else {
        if (q->front == -1) {
            q->front = 0; 
        }
        q->arr[++(q->rear)] = value;
        printf("%d enqueued to queue\n", value);
    }
}
int dequeue(struct Queue *q) {
    if (isEmpty(q)) {
        printf("Queue is empty! Cannot dequeue\n");
        return -1; 
    } else {
        int value = q->arr[q->front++];
        if (q->front > q->rear) {
            q->front = q->rear = -1;
        }
        return value;
    }
}
int main() {
    struct Queue q; 
    initQueue(&q);  
    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);
    enqueue(&q, 40);
    enqueue(&q, 50);
    enqueue(&q, 60);
    printf("Dequeued element: %d\n", dequeue(&q));
    printf("Dequeued element: %d\n", dequeue(&q));
    printf("Dequeued element: %d\n", dequeue(&q));
    printf("Dequeued element: %d\n", dequeue(&q));
    printf("Dequeued element: %d\n", dequeue(&q));
    dequeue(&q);
    return 0;
}
```
Output:
```
10 enqueued to queue
20 enqueued to queue
30 enqueued to queue
40 enqueued to queue
50 enqueued to queue
Queue is full! Cannot enqueue 60
Dequeued element: 10
Dequeued element: 20
Dequeued element: 30
Dequeued element: 40
Dequeued element: 50
Queue is empty! Cannot dequeue
```
Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
