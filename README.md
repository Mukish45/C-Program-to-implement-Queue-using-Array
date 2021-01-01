#include<stdio.h>
#define N 10

int queue[N];
int front = -1;
int rear = -1;

int enqueue();
int dequeue();
void size();
void frontElement();
void display();
void printline();

void main()
{
    int c;
    do
    {
        printline();
        printf("\nEnter  1.Enqueue  2.Dequeue  3.Size  4.Front Element   5. Display  6.Stop:\t");
        scanf("%d", &c);
        printline();
        switch (c)
        {
        case 1:
            enqueue();
            break;
        case 2:
            dequeue();
            break;
        case 3:
            size();
            break;
        case 4:
            frontElement();
            break;
        case 5:
            display();
            break;
        case 6:
            printf("\nExit!!!\n");
            printline();
            break;
        default:
            printf("\nInvalid entry!!!\n");
            printline();
        }
    }
    while(c!=6);
}

int enqueue()
{
    if(rear > N-1)
    {
        printf("\nOverflow condition\n");
        printline();
    }
    else if(rear ==-1 && front ==-1)
    {
        int a;
        rear++;
        front++;
        printf("\nEnter the element:\t");
        scanf("%d", &a);
        queue[rear] = a;
        rear++;
        printline();
    }
    else
    {
        int b;
        printf("\nEnter the element:\t");
        scanf("%d", &b);
        queue[rear] = b;
        rear++;
        printline();
    }
}

int dequeue()
{
    if(front == -1 && rear == -1)
    {
        printf("\n\t\tUnderflow condition\n");
        printline();
    }
    else if(front > N-1)
    {
        printf("\n\t\tAll the elements are dequeued\n");
        printline();
    }
    else if(front > rear)
    {
        printf("\nAll the entered elements in the queue are dequeued. Please Enqueue\n");
    }
    else
    {
        printf("\n\t\tThe dequeued element is %d",queue[front]);
        front++;
        printline();
    }
}

void size()
{
    if(front==-1 && rear==-1)
    {
        printf("\n\t\tUnderflow condition\n");
        printline();
    }
    else if(front>N-1 || front == rear)
    {
        printf("\n\t\tThe queue elements are dequeued\n");
        printline();
    }
    else
    {
        int x;
        x = rear - front;
        printf("\n\t\tThe size of the queue is %d",x);
        printline();
    }
}

void frontElement()
{
    if(front==-1 && rear==-1)
    {
        printf("\n\t\tUnderflow Condition\n");
        printline();
    }
    else if(front>N-1 || front == rear)
    {
        printf("\n\t\tThe queue elements are dequeued\n");
        printline();
    }
    else
    {
        int x;
        x = queue[front];
        printf("\n\t\tThe front element is %d",x);
        printline();
    }
}

void display()
{
    int i;
    if (front == -1 && rear == -1)
    {
        printf("\n\t\tUnderflow condition\n");
        printline();
    }
    else if(front > N-1 || front == rear)
    {
        printf("\n\t\tAll the elements are dequeued. No elements to display\n");
        printline();
    }
    else
    {
        printf("\n\tThe elements in the queue are:\t");
        for (i = front; i < rear; i++)
        {
            printf("%d \t", queue[i]);
        }
        printline();
    }
}

void printline()
{
    printf("\n------------------------------------------------------------------------------------------\n");
}
