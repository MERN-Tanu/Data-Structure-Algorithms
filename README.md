<img width="928" alt="linkedlist_for_more_understanding" src="https://user-images.githubusercontent.com/70361516/233584444-f47339dd-a8ea-4419-8972-293e0869f815.png">
# Data_Structure_algorithms

Topic:

Linkedlist : Collection of Nodes;


// How to create Node

#include <iostream>
using namespace std;

 class Node{
   public:
     int data;
     Node* next;

     Node()
     {
       this->data = 0;
       this->next =NULL;
     }

     Node(int data)
     {
       this->data = data;
       this->next = NULL;
     }

 };
 

 void print(Node* head)
 { 
     
 Node* temp = head;
   
 while(temp != NULL)
    {
 
     cout<<temp->data<<" ";
 
     temp = temp -> next;
 
    }

 }
 
int main() {
     
     Node* first = new Node(10);
     Node* second = new Node(20);
     Node* third = new Node(30);
     Node* fourth = new Node(40);
     Node* five = new Node(50);

     first->next = second;
     second->next = third;
     third->next = fourth;
     fourth->next = five;

     cout<<"printing the linkedlist"<<endl;
     print(first);


  return 0;
}
