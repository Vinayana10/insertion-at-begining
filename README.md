# insertion-at-begining

#include <stdio.h>
#include <stdlib.h>

struct node{
    int data;
    struct node* next;
};

int main()
{
   struct node *head = NULL, *temp = NULL, *newnode = NULL;
   int n,value;
   printf("enter the number of nodes");
   scanf("%d",&n);
   for(int i=0;i<n;i++)
   {
       newnode = (struct node*)malloc(sizeof(struct node));
       if(newnode == NULL)
       {
           printf("memory allocation failed,\n");
           return 1;
       }
       printf("enter data for node %d:",i+1);
       scanf("%d",&value);
       newnode->data = value;
       newnode->next = NULL;
       
       if(head == NULL){
           head = newnode;
           temp = newnode;
           
       }else{
           temp->next = newnode;
           temp = newnode;
       }
   }
   
  //insertion at the begining
  newnode = (struct node*)malloc(sizeof(struct node));
  if(newnode == NULL){
      printf("memory allocaiton failed for insertion.\n");
      return 1;
      
  }
  printf("enter data to insert at beginning:");
  scanf("%d",&value);
  newnode->data = value;
  newnode->next = head;
  head = newnode;
  
  
  //display the updated linked list
  printf("updated linked list (after insertion at beginning):");
  temp = head;
  while(temp != NULL){
      printf("%d->",temp->data);
      temp = temp->next;
      
  }
  printf("NULL\n");
  
    return 0;
}
