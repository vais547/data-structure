# data-structure

**1.Write  a c++ program to implement singly linked list.**

#include<iostream><br>
#include<cstdlib><br>
using namespace std;<br>
struct node<br>
{<br>
 int info;<br>
 struct node *next;<br>
}*start; <br>
class single_llist<br> 
{ <br>
 public:<br> 
 node* create_node(int);<br> 
 void insert_begin();<br>
 void insert_last();<br>
 void insert_pos();<br>
 void delete_begin();<br>
 void delete_last();<br>
 void delete_pos();<br>
 void update_begin();<br>
 void update_last();<br>
 void update_pos();<br>
 void sort(); <br>
 void reverse(); <br>
 void search(); <br>
 void display(); <br>
 single_llist() <br>
 { <br>
 start = NULL;<br> 
 } <br>
}; <br>
int main()<br> 
{ <br>
 int choice;<br> 
 single_llist sl,s2;<br> 
 start = NULL; <br>
 do <br>
 { <br>
 cout<<"---------------------------------"<<endl;<br> 
 cout<<"Operations on singly linked list"<<endl; <br>
 cout<<"---------------------------------"<<endl; <br>
 cout<<"1.Insert at first"<<endl; <br>
 cout<<"2.Insert at last"<<endl; <br>
 cout<<"3.Insert at position"<<endl; <br>
 cout<<"4.Delete at first"<<endl; <br>
 cout<<"5.Delete at Last"<<endl; <br>
 cout<<"6.Delete at position"<<endl; <br>
 cout<<"7.Update at first"<<endl; <br>
 cout<<"8.Update at last"<<endl;<br>
 cout<<"9.Update at position"<<endl;<br> 
 cout<<"10.Ascending order"<<endl; <br>
 cout<<"11.Descending order"<<endl; <br>
 cout<<"12.Search"<<endl; <br>
 cout<<"13.Display"<<endl; <br>
 cout<<"14.Exit "<<endl; <br>
 cout<<"Enter your choice :";<br> 
 cin>>choice; <br>
 switch(choice) <br>
 { <br>
 case 1: sl.insert_begin();<br> 
 sl.display(); <br>
 break; <br>
 case 2: sl.insert_last();<br> 
 sl.display(); <br>
 break; <br>
 case 3: sl.insert_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 4: s2.delete_begin(); <br>
 sl.display(); <br>
 break; <br>
 case 5: s2.delete_last();<br> 
 sl.display(); <br>
 break; <br>
 case 6: sl.delete_pos();<br> 
 sl.display(); <br>
 break; <br>
 case 7: sl.update_begin();<br> 
 sl.display(); <br>
 break; <br>
 case 8: sl.update_last();<br> 
 sl.display(); <br>
 break; <br>
 case 9: sl.update_pos();<br> 
 sl.display(); <br>
 break; <br>
 case 10:sl.sort();<br> 
 sl.display(); <br>
 break; <br>
 case 11:sl.reverse();<br> 
 sl.display(); <br>
 break; <br>
 case 12:sl.search();<br> 
 sl.display(); <br>
 break; <br>
 case 13:sl.display();<br> 
 break; <br>
 case 14:exit(0);<br> 
 break; <br>
 default:cout<<"Wrong choice...???"<<endl;<br> 
 break; <br>
 } <br>
 } <br>
 while(choice != 14);<br> 
} <br>
node *single_llist::create_node(int value)<br> 
{ <br>
 struct node *temp, *s;<br> 
 temp = new(struct node); <br>
 if (temp == NULL) <br>
 { <br>
 cout<<"Memory not allocated"<<endl; <br>
 return 0;<br> 
 } <br>
 else <br>
 { <br>
 temp->info = value; <br>
 temp->next = NULL; <br>
 return temp; <br>
 } <br>
} <br>
void single_llist::insert_begin() <br>
{ <br>
 int value; <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 struct node *temp, *s; <br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br>
 start = temp; <br>
 start->next = NULL; <br>
 cout<<temp->info<<" is inserted at first in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start; <br>
 start = temp; <br>
 start->next = s; <br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
} <br>
void single_llist::insert_last() <br>
{ <br>
 int value; <br>
 cout<<"Enter the value to be inserted : ";<br> 
 cin>>value; <br>
 struct node *temp, *s; <br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br>
 start = temp; <br>
 start->next = NULL; <br>
 cout<<temp->info<<" is inserted at last in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start; <br>
 while (s->next != NULL) <br>
 { <br>
 s = s->next; <br>
 } <br>
 temp->next = NULL;<br>
 s->next = temp; <br>
 cout<<temp->info<<" is inserted at last"<<endl; <br>
 } <br>
} <br>
void single_llist::insert_pos() <br>
{ <br>
 int value, pos, counter = 0, loc = 1; <br>
  struct node *temp, *s, *ptr; <br>
 s = start;  <br>
 while (s != NULL)  <br>
 {  <br>
s = s->next;  <br>
 counter++;  <br>
 }  <br>
 if (counter == 0){}  <br>
 else  <br>
 {  <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : ";  <br>
 cin>>pos;  <br>
 s = start;  <br>
 if(pos == 1)  <br>
 {  <br>
 cout<<"Enter the value to be inserted : ";  <br>
 cin>>value;  <br>
 temp = create_node(value);  <br>
  start = temp; <br>
 start->next = s; <br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
 else if (pos > 1 && pos <= counter)<br><br> 
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 for (int i = 1; i < pos; i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br><br>
 } <br>
 ptr->next = temp; <br>
 temp->next = s; <br>
 cout<<temp->info<<" is inserted at position "<<pos<<endl;<br> 
 } <br>
 else if (pos == counter+1) <br><br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br><br>
 cin>>value; <br>
 temp = create_node(value); <br>
 while (s->next != NULL) <br>
 { <br>
 s = s->next; <br><br>
 } <br>
 temp->next = NULL; <br>
 s->next = temp; <br>
 cout<<temp->info<<" is inserted at last"<<endl; <br><br>
 } <br>
 else <br>
 { <br>
 cout<<"Positon out of range...!!!"<<endl;<br>
 } <br>
 } <br>
} <br>
void single_llist::delete_begin()<br> 
{ <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
} <br>
void single_llist::delete_last()<br><br> 
{ <br>
 int i, counter = 0; <br><br>
 struct node *s, *ptr; <br>
 if (start == NULL){} <br>
 else <br>
 { <br><br>
 s = start; <br>
 while (s != NULL) <br><br>
 { <br>
 s = s->next;<br>
 counter++; <br>
 } <br>
 s = start; <br>
 if (counter == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from last"<<endl; <br>
 free(s); <br>
 } <br>
 else <br>
 { <br>
 for (i = 1;i < counter;i++) <br>
 { <br>
 ptr = s; <br><br>
 s = s->next; <br>
 } <br><br><br>
 ptr->next = s->next; <br><br>
 cout<<s->info<<" deleted from last"<<endl; <br>
 free(s); <br>
 } <br>
 } <br>
} <br>
void single_llist::delete_pos() <br>
{ <br>
 int pos, i, counter = 0, loc = 1;<br> 
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next;<br> 
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 if (counter == 1) <br>
 { <br>
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl;<br> 
 free(s); <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br><br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 for (i = 1;i < pos;i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = s->next; <br>
 if(pos == counter) <br>
 {cout<<s->info<<" deleted from last"<<endl; <br>
 free(s);} <br>
 else <br>
 {cout<<s->info<<" deleted from postion "<<pos<<endl; <br><br>
 free(s);} <br>
 } <br>
 else <br><br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_llist::update_begin() <br>
{<br> 
 int value, pos=1, i,counter = 0; <br>
 struct node *s, *ptr; <br>
 s = start; <br><br>
 while (s != NULL) <br>
 { <br>
 s = s->next;<br> 
 counter++; <br>
 } <br>
 if (counter == 0){}<br> 
 else if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at first position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br><br>
} <br>
void single_llist::update_last() <br>
{ <br>
 int value, pos, i,counter = 0; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 s=start; <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < counter ; i++) <br>
 { <br>
 s = s->next; <br>
 } <br><br>
 s->info = value; <br>
 cout<<"Node updated at last position : "<<counter<<" = "<<s->info<<endl; <br>
 } <br>
} <br>
void single_llist::update_pos() <br>
{ <br>
 int value, pos, i,counter = 0, loc = 1; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
{ <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 if (counter == 1) <br>
 { <br>
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < pos ; i++) <br>
 { <br>
 s = s->next; <br><br>
 } <br>
 s->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<s->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
 
void single_llist::sort() <br>
{ <br>
 struct node *ptr, *s; <br>
 int value; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 ptr = start; <br>
while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br>
 { <br>
 if (ptr->info > s->info) <br>
 { <br>
 value = ptr->info; <br><br>
 ptr->info = s->info; <br>
 s->info = value; <br>
 } <br>
 } <br>
 ptr = ptr->next; <br>
 } <br><br>
 } <br>
} <br>
void single_llist::reverse() <br>
{ <br>
 struct node *ptr, *s; <br>
 int value; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 ptr = start; <br>
 while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br><br>
 { <br>
 if (ptr->info < s->info) <br>
 { <br>
 value = ptr->info; <br>
 ptr->info = s->info; <br>
 s->info = value; <br>
 } <br>
 } <br>
 ptr = ptr->next; <br>
 } <br>
 } <br>
} <br>
void single_llist::search()<br> 
{ <br>
 int value, loc = 0, pos = 0, counter = 0; <br>
 struct node *s; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 cout<<"Enter the value to be searched : "; <br><br>
 cin>>value; <br>
 struct node *s; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 pos++; <br>
if (s->info == value) <br>
 { <br>
 loc++; <br>
 if(loc == 1) <br>
 cout<<"Element "<<value<<" is found at position "<<pos; <br>
 else if(loc <= counter) <br>
 cout<<" , "<<pos; <br>
 } <br>
 s = s->next; <br><br>
 } <br>
 cout<<endl; <br>
 if (loc == 0) <br>
 cout<<"Element "<<value<<" not found in the list"<<endl; <br>
 } <br>
} <br>
void single_llist::display() <br>
{ <br><br>
 struct node *temp; <br>
 if (start == NULL) <br>
 cout<<"Linked list is empty...!!!"<<endl; <br>
 else <br>
 { <br>
 cout<<"Linked list contains : "; <br>
 temp = start;  <br>
 while (temp != NULL) <br>
 {  <br>
 cout<<temp->info<<" "; <br> 
 temp = temp->next; <br> 
 }  <br>
} <br>
} <br>

 output:
 
![image](https://user-images.githubusercontent.com/98145574/152737321-c351271f-7d25-49af-b245-31544cfbc85e.png)<br>
![image](https://user-images.githubusercontent.com/98145574/152737471-ad805d2a-1e72-4790-b824-abf6f4faca30.png)<br>
![image](https://user-images.githubusercontent.com/98145574/152737723-e1cd1ebf-24e6-44f2-abf9-73871b9dd58b.png)<br>
![image](https://user-images.githubusercontent.com/98145574/152737820-a7b11a41-3e01-4ea2-b67d-0c99b944dc12.png)<br>
![image](https://user-images.githubusercontent.com/98145574/152737900-eef459ff-238e-44d4-9cbd-bff0ab7956d5.png)<br>
![image](https://user-images.githubusercontent.com/98145574/152737959-7992852d-c4ac-4228-bc50-83ba1b8d4f5c.png)<br>
![image](https://user-images.githubusercontent.com/98145574/152738065-21565d78-983c-4823-8aaa-48a6c0508344.png)<br>
![image](https://user-images.githubusercontent.com/98145574/152738709-35628121-5ad4-41c9-8bcd-f347990743eb.png)<br>

** 2.write a c++ program to implement single linked list.**<br>
 
 #include <iostream><br>
#include <cstdlib><br>
using namespace std;<br>
struct Node {<br>
   int data;<br>
   struct Node *next;<br>
};<br>
struct Node* head = NULL;<br>
void insert(int new_data) {<br>
   struct Node* new_node = (struct Node*) malloc(sizeof(struct Node));<br>
   new_node->data = new_data;<br>
   new_node->next = head;<br>
   head = new_node;<br>
   }<br>
void display() {<br>
   struct Node* ptr;<br>
   ptr = head;<br>
   while (ptr != NULL) {<br>
      cout<< ptr->data <<" ";<br>
      ptr = ptr->next;<br>
   }<br>
}<br>
int main() <br>
{<br>
   insert(3);<br>
   insert(1);<br>
   insert(7);<br>
   insert(2);<br>
   insert(9);<br>
    cout<<"The linked list is: ";<br>
   display();<br>
   return 0;<br>
}<br>
 output:<br>
 ![image](https://user-images.githubusercontent.com/98145574/152923023-63035939-2cf1-4a61-abaf-d8da71ce1997.png)<br><br>

 **3.write a c++ program to implement insertion and deletion node in a front position.**<br>
 
 #include<iostream><br>
#include<cstdlib><br>
using namespace std;<br>
struct node<br>
{<br>
int info;<br>
struct node *next;<br>
}*start;<br>
class single_llist<br>
{<br>
	public:<br>
	node* create_node(int);<br>
	void insert_begin();<br>
	void delete_begin();<br>
	void display();<br>
	single_llist()<br>
	{<br>
		start=NULL;<br>
	}<br>
	
};<br>
int main()<br>
{<br>
	int choice;<br>
	single_llist s1,s2;<br>
	start=NULL;<br>
	do<br>
	{<br>
		cout<<"___________"<<endl;<br>
		cout<<"operations on single linked list"<<endl;<br>
	    cout<<"___________"<<endl;<br>
	    cout<<"1.Insert at first"<<endl;<br>
	    cout<<"2.Delete at first"<<endl;<br>
	    cout<<"3.Display"<<endl;<br>
	    cout<<"4.Exit "<<endl;<br>
        cout<<"Enter your choice :";<br>
        cin>>choice;<br>
        switch(choice)<br>
        {<br>
           case 1:s1.insert_begin();<br>
            s1.display();<br>
            break;<br>
            case 2:s2.delete_begin();<br>
            s1.display();<br>
            break;<br>
            case 3:s1.display();<br>
            break;<br>
            case 4:exit(0);<br>
            break;<br>
            default:cout<<"Wrong choice...???"<<endl;<br>
            break;<br>
	    }<br>
    }<br>
while(choice !=4);<br>
}<br>
node *single_llist::create_node(int value)<br>
{<br>
	struct node *temp, *s;<br>
    temp = new(struct node);<br>
    if (temp == NULL)<br>
{<br>
cout<<"Memory not allocated"<<endl;<br>
return 0;<br>
}<br>
else<br>
{<br>
temp->info = value;<br>
temp->next = NULL;<br>
return temp;<br>
}<br>
}<br>
void single_llist::insert_begin()<br>
{<br>
int value;<br>
cout<<"Enter the value to be inserted : ";<br>
cin>>value;<br>
struct node *temp, *s;<br>
temp = create_node(value);<br>
if (start == NULL)<br>
{<br>
start = temp;<br>
start->next = NULL;<br>
cout<< temp->info<<" is inserted at first in the empty list"<<endl;<br>
}<br>
else<br>
{<br>
s = start;<br>
start = temp;<br>
start->next = s;<br>
cout<<temp->info<<" is inserted at first"<<endl;<br>
}<br>
}<br>
void single_llist::delete_begin()<br>
{<br>
if (start == NULL){}<br>
else<br>
{<br>
struct node *s, *ptr;<br>
s = start;<br>
start = s->next;<br>
cout<<s->info<<" deleted from first"<<endl;<br><br>
free(s);<br>
}<br>
}<br>
void single_llist::display()<br>
{<br>
struct node *temp;<br><br>
if (start == NULL)<br>
cout<<"Linked list is empty...!!!"<<endl;<br>
else<br>
{<br>
cout<<"Linked list contains : ";<br><br>
temp = start;<br>
while (temp != NULL)<br>
{<br>
cout<<temp->info<<" ";<br>
temp = temp->next;<br>
}<br>
cout<<endl;<br>
}<br>
}<br>
 
 
 ![image](https://user-images.githubusercontent.com/98145574/152937715-49d777ba-2249-4672-85b6-8b0531365dca.png)<br>
 ![image](https://user-images.githubusercontent.com/98145574/152937820-d823edac-2e91-4755-93c4-19bdbcd79474.png)<br>

**3.Write a C++ program to split the linked list into two halves such that the element ‘e’ should be the first element of second list.**<br><br>
#include<iostream><br>
using namespace std;<br>
struct Node{<br>
	int value;<br>
	struct Node *next;<br>
};<br>
 struct Node* head=NULL;<br>
 struct Node* sHead=NULL;<br>
 struct Node* temp=NULL;<br>
 void insert(int new_data){<br>
 	struct Node* new_node=new Node();<br>
 	new_node->value=new_data;<br>
 	new_node->next=head;<br>
 	head=new_node;<br>
 }<br>
 int n;<br>
 int e;<br>
 int splitIndex;<br>
 int main(){<br>
 	int i;<br>
 	cout<<"enter number of elements you want in the list\t";<br>
 	cin>>n;<br>
 	cout<<"Enter elements:"<<endl;<br>
 	for(i=0;i<n;i++){<br>
 		cin>>e;<br>
 		insert(e);<br>
	 }<br>
	 cout<<"\nList of elements : "<<endl;<br>
	 Node *t;<br>
	 t=head;<br>
	 while(t!=NULL){<br>
	 cout<<t->value<<"\t";<br>
	 t=t->next;<br>
	 
 }<br>
 cout<<"\n\nEnter the position you want to split";<br>
 cin>>splitIndex;<br>
 while(splitIndex<0||splitIndex>n-1){<br>
 	cout<<"Invalied position.Try again."<<endl;<br>
 	cin>>splitIndex;<br>
 }<br>
 temp=head;<br>
 for(i=0;i<=splitIndex;i++){<br>
	if(i==splitIndex-1){<br>
 		Node *tN;<br>
 		tN=temp->next;<br>
 		sHead=tN;<br>
 		temp->next=NULL;<br>
 		break;<br>
 		 }<br>
	 temp=temp->next;<br>
 }<br>
 temp=head;<br>
 if(temp==NULL){<br>
 	cout<<"\nFirst list is empty"<<endl;<br>
 	}else{<br>
 		cout<<"\n\nFirst list Element"<<endl;<br>
 		while(temp!=NULL){<br>
 			cout<<temp->value<<"\t";<br>
 			temp=temp->next;<br>
		 }<br>
	 }<br>
	 temp=sHead;<br>
	 if(temp==NULL){<br>
	 	cout<<"\nSecond list is empty"<<endl;<br>
	 }else{<br>
	 	cout<<"\n\nSecond list elements "<<endl;<br>
	 	 while(temp != NULL){<br>
	        cout<<temp->value<<"\t";<br>
                 temp = temp->next;<br>
	}<br>
	 }<br>
	 return 0;<br>
      }<br>
 **output:**<br>
	![image](https://user-images.githubusercontent.com/98145574/155928940-739ef3a9-75d2-4e68-ad33-d73504a0febc.png)<br>
	![image](https://user-images.githubusercontent.com/98145574/155928989-fb10dd98-ee94-41eb-9274-7dfd627c5b75.png)<br>
	
**4.Write a program to store k keys into an array of size n at the location compute using a hash function, loc=key%n, where k<=n and  key takes values from [1 to m], m>n. Handle the collision using Linear Probing technique.	**<br>
#include<iostream><br>
#include<limits.h><br>
using namespace std;<br>
void Insert(int ary[],int hFn, int Size){<br>
    int element,pos,n=0;<br>
cout<<"Enter key element to insert\n";<br>
cin>>element;<br>
pos = element%hFn;<br>
while(ary[pos]!= INT_MIN) {<br>
if(ary[pos]== INT_MAX)<br>
            break;<br>
pos = (pos+1)%hFn;<br>
n++;<br>
if(n==Size)<br>
            break;<br>   
}<br>
if(n==Size)<br>
        cout<<"Hash table was full of elements\nNo Place to insert this element\n\n";<br>
else<br>
        ary[pos] = element;<br>   
}<br>
void display(int ary[],int Size){<br>
int i;<br>
 
cout<<"Index\tValue\n";<br>
for(i=0;i<Size;i++)<br>
        cout<<i<<"\t"<<ary[i]<<"\n";<br>
}<br>
int main(){<br>
int Size,hFn,i,choice;<br>
cout<<"Enter size of hash table\n";<br>
cin>>Size;<br>
 hFn=Size;<br>
int ary[Size];<br>
for(i=0;i<Size;i++)<br>
        ary[i]=INT_MIN;<br>
do{<br>
cout<<"Enter your choice\n";<br>
cout<<" 1-> Insert\n 2-> Display\n 0-> Exit\n";<br>
cin>>choice;<br>
switch(choice){<br>
case 1:<br>
Insert(ary,hFn,Size);<br>
break;<br><br>
case 2:<br>
display(ary,Size);<br>
break;<br>
default:<br>
cout<<"Enter correct choice\n";<br>
break;<br>
}<br>
}while(choice);<br>
return 0;<br>
}<br>
**output:**<br>
	![image](https://user-images.githubusercontent.com/98145574/155930324-8cbccc21-219e-47c6-98b7-2e521dab4902.png)<br><br>



 

