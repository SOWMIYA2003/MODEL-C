# C12-STACK USING LINKED LIST/QUEUE USING LINKED LIST
## STACK USING LINKED LIST
### DISPLAY 
```
struct Node   
{  
int data;  
struct Node *next;  
}*head;  
void display()  
{  
    struct Node *ptr;
    ptr=head;
    while(ptr!=NULL)
    {
        printf("%d\n",ptr->data);
        ptr=ptr->next;
    }
}
```
### PEEK 
```
struct Node   
{  
int data;  
struct Node *next;  
}*head;
void peek()
{
    printf("%d\n",head->data);
}
```
### POP 
```
struct Node   
{  
int data;  
struct Node *next;  
}*head;  
void pop()  
{ 
    struct Node *ptr;
    if(head==NULL)
    {
        printf("stack is empty");
    }
    else
    {
        ptr=head;
        head=ptr->next;
        free(ptr);
    }
}
```
### PUSH
```
struct Node   
{  
double data;  
struct Node *next;  
}*head;
void push(double data)  
{  
    struct Node *p=(struct Node*)malloc(sizeof(struct Node));
    if(head==NULL)
    {
        p->data=data;
        p->next=NULL;
        head=p;
    }
    else{
        
        p->data=data;
        p->next=head;
        head=p;
    }
}
```
## QUEUE USING LINKED LIST
### DISPLAY 
```
struct Node
{
   float data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void display()
{
    if (front==NULL)
    {
        printf("queue is empty\n");
    }
    else{
        printf("queue elements:\n");
        struct Node *t;
        t=front;
        while(t!=NULL)
        {
            printf("%.2f\n",t->data);
            t=t->next;
        }
    }
}
```
### PEEK 
```
struct Node
{
   float data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void peek()
{
    printf("%.2f\n",front->data);
}
```
### DEQUEUE
```
struct Node
{
   float data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void dequeue()
{
    if(front==NULL)
    {
        printf("Queue is Empty!!!\n");
    }
    else{
        struct Node *t=front;
        front=front->next;
        free(t);
    }
}
```
### ENQUEUE 
```
struct Node
{
    float data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void enqueue(float data)
{
    struct Node *nn;
    nn=(struct Node*)malloc(sizeof(struct Node));
    nn->data=data;
    nn->next=NULL;
    if(front==NULL)
    {
        front=rear=nn;
    }
    else{
        rear->next=nn;
        rear=nn;
    }
}
```
