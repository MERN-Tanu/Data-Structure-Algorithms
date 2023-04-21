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
 
 ---------------------output------------
 
 printing the ll 
 
 10 20 30 40 50
 
 -------------Insertion IN THE linkeddlist ---------------
 
 #include<iostream>
 
using namespace std;
 

class   Node 
 
 {
 
        public:
 
        int data;
 
        Node* next;

        Node() {
                this->data = 0;
                this->next = NULL;
        }
        Node(int data) {
                this->data = data;
                this->next = NULL;
        }
};

 
//I want to insert a node right at the head of Linked List
 
 
void insertAtHead(Node* &head, Node* &tail, int data)
 {
        
 //check for Empty LL
 
        if(head == NULL) {
 
                Node* newNode = new Node(data);
 
                head = newNode;
 
                tail = newNode;
        }
 
        else {
 
                //step1:
 
                Node* newNode = new Node(data);
 
                //step2:
 
                newNode -> next = head;
 
                //step3:
 
                head = newNode;
        }


}
 
//I want to insert a node right at the end of LINKED LIST
 
void insertAtTail(Node* &head,Node* &tail, int data)  
 
 {
        if(head == NULL) {
 
 
                Node* newNode = new Node(data);
 
                head = newNode;
 
                tail = newNode;
 
                return;
        }
 
        //step1: creatae a node
 
        Node* newNode = new Node(data);
 
        //step2: connect woth tail ndoe
 
        tail->next = newNode;
 
        //step3: update tail;
 
        tail = newNode;
}
 
void print(Node* head) {
 

        Node* temp = head;
 
        while(temp != NULL) {
 
                cout << temp->data << " ";
 
                temp = temp->next;
        }
}

int findLength(Node* &head ) {
 
        int len = 0;
 
        Node* temp = head;
 
        while(temp != NULL) {
 
                temp = temp->next;
 
                len++;
        }
 
        return len;
}

void insertAtPosition(int data, int position, Node* &head, Node* &tail) 
 
 { 
 
        if(head == NULL) {
 
 
                Node* newNode = new Node(data);
 
                head = newNode;
 
                tail = newNode;
 
                return;
        }
 
        //step1: find the position: prev & curr;

        if(position == 0) {
 
                insertAtHead(head, tail , data);
 
                return;
        }
       
        int len = findLength(head);
 
        
        if(position >= len) {
 
                insertAtTail(head, tail, data);
 
                return;
        }
        //ste1:find prev and curr
 
        int i = 1;
 
        Node* prev = head;
 
        while(i < position) {
                           
                prev= prev -> next;
 
                i++;
        }
 
        Node* curr = prev -> next;

        //step2;
 
        Node* newNode = new Node(data);

        //step3:
 
        newNode -> next = curr;

        //step4:
 
        prev -> next = newNode;
}

int main() 
 {

        Node* head = NULL;
 
        Node* tail = NULL;
 
        insertAtHead(head, tail,20);
 
        insertAtHead(head, tail,50);
 
        insertAtHead(head, tail,60);
 
        insertAtHead(head,tail, 90);
 
        insertAtTail(head, tail, 77);
 

        print(head);
 
        cout << endl;
 
        // cout << "head: " << head -> data << endl;
 
        // cout << "tail: " << tail->data << endl;

        insertAtPosition(101, 5, head, tail);
 
        cout<< "Printing after insert at position call" << endl;
 
        print(head);
 
        cout << endl;
 
        cout << "head: " << head -> data << endl;
 
 
        cout << "tail: " << tail->data << endl;

        return 0;
}
 
 
