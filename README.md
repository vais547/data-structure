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

**2.Write a C++ program to split the linked list into two halves such that the element ‘e’ should be the first element of second list.**<br><br>
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
	
**3.Write a program to store k keys into an array of size n at the location compute using a hash function, loc=key%n, where k<=n and  key takes values from [1 to m], m>n.Handle the collision using Linear Probing technique.**<br>
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
	![image](https://user-images.githubusercontent.com/98145574/155931182-a9a6fa50-ccf6-4472-9429-4a6878780587.png)<br>

**4.C++ program to implement doubly linked list.**<br>
#include <iostream><br>
using namespace std;<br>
struct Node {<br>
   int data;<br>
   struct Node *prev;<br>
   struct Node *next;<br>
};<br>
struct Node* head = NULL;<br>
void insert(int newdata) {<br>
   struct Node* newnode = (struct Node*) malloc(sizeof(struct Node));<br>
   newnode->data = newdata;<br>
   newnode->prev = NULL;<br>
   newnode->next = head;<br>
   if(head != NULL)<br>
   head->prev = newnode ;<br>
   head = newnode;<br>
}<br>
void display() {<br>
   struct Node* ptr;<br>
   ptr = head;<br>
   while(ptr != NULL) {<br>
      cout<< ptr->data <<" ";<br>
      ptr = ptr->next;<br>
   }<br>
}<br>
int main() {<br>
   insert(3);<br>
   insert(1);<br>
   insert(7);<br>
   insert(2);<br>
   insert(9);<br>
   cout<<"The doubly linked list is: ";<br>
   display();<br>
   return 0;<br>
}<br>
	
**output:**<br>
	![image](https://user-images.githubusercontent.com/98145574/155932947-3efe5adc-9f61-4ec5-9501-ca2ca23a7f2f.png)<br><br>
	
**5.write a C++ program to implementing the Heap sort technique.**<br>
#include <iostream><br>
using namespace std;<br>
void MaxHeapify (int a[], int i, int n)<br>
{<br>
	int j, temp;<br>
	temp = a[i];<br>
	j = 2*i;<br>
	while (j <= n)<br>
	{<br><br>
		if (j < n && a[j+1] > a[j])<br>
		j = j+1;<br>
		if (temp > a[j])<br>
			break;<br>
		else if (temp <= a[j])<br>
		{<br><br>
			a[j/2] = a[j];<br>
			j = 2*j;<br>
		}<br>
	}<br>
	a[j/2] = temp;<br>
	return;<br>
}<br>
void HeapSort(int a[], int n)<br>
{<br>
	int i, temp;<br>
	for (i = n; i >= 2; <br>
{<br>
		temp = a[i];<br>
		a[i] = a[1];<br>
		a[1] = temp;<br>
		MaxHeapify(a, 1, i - 1);<br>
	}<br>
}<br>
void Build_MaxHeap(int a[], int n)<br>
{<br>
	int i;<br>
	for(i = n/2; i >= 1; i--)<br>
		MaxHeapify(a, i, n);<br>
}<br>
int main()<br>
{<br>
int n, i,arr[100];<br>
	cout<<"\nEnter the number of data element to be sorted: ";<br>
	cin>>n;<br>
	n++;<br>
	for(i=1;i<n;i++)<br>
	 {<br>
	 cout<<"Enter element"<<i<<":";<br>
	 cin>>arr[i];<br>
	 }<br>
	Build_MaxHeap(arr, n-1);<br>
	HeapSort(arr, n-1);<br>
	cout<<"\nSorted Data ";<br>
	for (i = 1; i < n; i++)<br>
		cout<<" "<<arr[i];<br>
	return 0;<br>
}<br>
 **output:**<br>
	![image](https://user-images.githubusercontent.com/98145574/155939736-a3199d29-4192-4d69-8a17-5ba244200643.png)<br>
	
**6.program to create minimum and maximum heap.**<br>
	
#include <iostream><br>
#include <conio.h><br>
using namespace std;<br>
void max_heapify(int *a, int i, int n)<br>
{<br>
    int j, temp;<br>
    temp = a[i];<br>
    j = 2 * i;<br>
    while (j <= n)<br>
    {<br>
        if (j < n && a[j+1] > a[j])<br>
            j = j + 1;<br>
        if (temp > a[j])<br>
            break;<br>
        else if (temp <= a[j])<br>
        {<br>
            a[j / 2] = a[j];<br>
            j = 2 * j;<br>
        }<br>
    }<br>
    a[j/2] = temp;<br>
    return;<br>
}<br>
void build_maxheap(int *a,int n)<br>
{<br>
    int i;<br>
    for(i = n/2; i >= 1; i--)<br>
    {<br>
        max_heapify(a,i,n);<br>
    }<br>
}<br>

void min_heapify(int *a,int i,int n)<br>
{<br>
    int j, temp;<br>
    temp = a[i];<br>
    j = 2 * i;<br>
    while (j <= n)<br>
    {<br>
        if (j < n && a[j+1] < a[j])<br>
            j = j + 1;<br>
        if (temp < a[j])<br>
            break;<br>
        else if (temp >= a[j])<br>
        {<br>
            a[j/2] = a[j];<br>
            j = 2 * j;<br>
        }<br>
    }<br>
    a[j/2] = temp;<br>
    return;<br>
}<br>
void build_minheap(int *a, int n)<br>
{<br>
    int i;<br>
    for(i = n/2; i >= 1; i--)<br>
    {<br>
        min_heapify(a,i,n);<br>
    }<br>
}<br>

int main()<br>
{<br>
    int n, i, x;<br>
    cout<<"enter no of elements of array\n";<br>
    cin>>n;<br>
    int a[20];<br>
    for (i = 1; i <= n; i++)<br>
    {<br>
        cout<<"enter element"<<(i)<<endl;<br>
        cin>>a[i];<br>
    }<br>
     build_maxheap(a,n);<br>
    cout<<"Max Heap\n";<br>
    for (i = 1; i <= n; i++)<br>
    {<br>
        cout<<a[i]<<endl;<br>
    }<br>
     build_minheap(a, n);<br>
    cout<<"Min Heap\n";<br>
    for (i = 1; i <= n; i++)<br>
    {<br>
        cout<<a[i]<<endl;<br>
    }<br>
    getch();<br>
}<br>

**output:**<br>
![image](https://user-images.githubusercontent.com/98145574/156986211-8144ed34-a707-41b3-b18d-2313a89c69a6.png)<br>

**7.program to create a sum of subsets using backtracking.**<br>
#include<iostream><br>
using namespace std;<br>
int s[10],d,n,set[10],count=0;<br>
void display(int);<br>
int flag = 0;<br>
int main()<br>
{<br>
int subset(int,int);<br>
int i;<br>
cout<<"enter the number f elements in he set :";<br>
cin>>n;<br>
cout<<"Enter the set of values:";<br>
for(i=0;i<n;i++)<br>
cin>>s[i];<br>
cout<<"Enter the sum:";<br>
cin>>d;<br>
cout<<"The program output is:";<br>
subset(0 , 0);<br>
if(flag == 0)<br>
cout<<"There is no solution:";<br>
}<br>
int subset(int sum,int i)<br>
{<br>
if(sum == d)<br>
{<br>
flag = 1;<br>
display(count);<br>
return 0;<br>
}<br>
if(sum>d || i>=n)<br>
return 1;<br>
else<br>
 {<br>
set[count]=s[i];<br>
count++;<br>
subset(sum+s[i],i+1);<br>
count--;<br>
subset(sum,i+1);<br>
 }<br>
}<br>
void display(int count)<br>
{<br>
int i;<br>
cout<<"\t { ";<br>
for(i=0;i<count;i++)<br>
cout<<"}";<br>
}<br>
	
**output:**<br>
![image](https://user-images.githubusercontent.com/98145574/157182720-7c1a4f99-18c6-4b7c-9cc7-de04fecfe927.png)<br>
	
**8.write a program to insertion into AVL tree and deletion from an AVL tree.**<br>
#include<iostream><br>
#include<cstdio><br>
#include<sstream><br>
#include<algorithm><br>
#define pow2(n) (1 << (n))<br>
using namespace std;<br>
struct avl {<br>
   int d;<br>
   struct avl *l;<br>
   struct avl *r;<br>
}*r;<br>
class avl_tree {<br>
   public:<br>
      int height(avl *);<br>
      int difference(avl *);<br>
      avl *rr_rotat(avl *);<br>
      avl *ll_rotat(avl *);<br>
      avl *lr_rotat(avl*);<br>
      avl *rl_rotat(avl *);<br>
      avl * balance(avl *);<br>
      avl * insert(avl*, int);<br>
      void show(avl*, int);<br>
      void inorder(avl *);<br>
      void preorder(avl *);<br>
      void postorder(avl*);<br>
      avl_tree() {<br>
         r = NULL;<br>
      }<br>
};<br>
int avl_tree::height(avl *t) {<br>
   int h = 0;<br>
   if (t != NULL) {<br>
      int l_height = height(t->l);<br>
      int r_height = height(t->r);<br>
      int max_height = max(l_height, r_height);<br>
      h = max_height + 1;<br>
   }<br>
   return h;<br>
}<br>
int avl_tree::difference(avl *t) {<br>
   int l_height = height(t->l);<br>
   int r_height = height(t->r);<br>
   int b_factor = l_height - r_height;<br>
   return b_factor;<br>
}<br>
avl *avl_tree::rr_rotat(avl *parent) {<br>
   avl *t;<br>
   t = parent->r;<br>
   parent->r = t->l;<br>
   t->l = parent;<br>
   cout<<"Right-Right Rotation";<br>
   return t;<br>
}<br>
avl *avl_tree::ll_rotat(avl *parent) {<br>
   avl *t;<br>
   t = parent->l;<br>
   parent->l = t->r;<br>
   t->r = parent;<br>
   cout<<"Left-Left Rotation";<br>
   return t;<br>
}<br>
avl *avl_tree::lr_rotat(avl *parent) {<br>
   avl *t;<br>
   t = parent->l;<br>
   parent->l = rr_rotat(t);<br>
   cout<<"Left-Right Rotation";<br>
   return ll_rotat(parent);<br>
}<br>
avl *avl_tree::rl_rotat(avl *parent) {<br>
   avl *t;<br>
   t = parent->r;<br>
   parent->r = ll_rotat(t);<br>
   cout<<"Right-Left Rotation";<br>
   return rr_rotat(parent);<br>
}<br>
avl *avl_tree::balance(avl *t) {<br>
   int bal_factor = difference(t);<br>
   if (bal_factor > 1) {<br>
      if (difference(t->l) > 0)<br>
         t = ll_rotat(t);<br>
      else<br>
         t = lr_rotat(t);<br>
   } else if (bal_factor < -1) {<br>
      if (difference(t->r) > 0)<br>
         t = rl_rotat(t);<br>
      else<br>
         t = rr_rotat(t);<br>
   }<br>
   return t;<br>
}<br>
avl *avl_tree::insert(avl *r, int v) {<br>
   if (r == NULL) {<br>
      r = new avl;<br>
      r->d = v;<br>
      r->l = NULL;<br>
      r->r = NULL<br>
      return r;<br>
   } else if (v< r->d) {<br>
      r->l = insert(r->l, v);<br>
      r = balance(r);<br>
   } else if (v >= r->d) {<br>
      r->r = insert(r->r, v);<br>
      r = balance(r);<br>
   } return r;<br>
}<br>
void avl_tree::show(avl *p, int l) {<br>
   int i;<br>
   if (p != NULL) {<br>
      show(p->r, l+ 1);<br>
      cout<<" ";<br>
      if (p == r)<br>
         cout << "Root -> ";<br>
      for (i = 0; i < l&& p != r; i++)<br>
         cout << " ";<br>
         cout << p->d;<br>
         show(p->l, l + 1);<br>
   }<br>
}<br>
void avl_tree::inorder(avl *t) {<br>
   if (t == NULL)<br>
      return;<br>
      inorder(t->l);<br>
      cout << t->d << " ";<br>
      inorder(t->r);<br>
}<br>
void avl_tree::preorder(avl *t) {<br>
   if (t == NULL)<br>
      return;<br>
      cout << t->d << " ";<br>
      preorder(t->l);<br>
      preorder(t->r);<br>
}<br>
void avl_tree::postorder(avl *t) {<br>
   if (t == NULL)<br>
      return;<br>
      postorder(t ->l);<br>
      postorder(t ->r);<br>
      cout << t->d << " ";<br>
}<br>
int main() {<br>
   int c, i;<br>
   avl_tree avl;<br>
   while (1) {<br>
      cout << "1.Insert Element into the tree" << endl;<br>
      cout << "2.show Balanced AVL Tree" << endl;<br>
      cout << "3.InOrder traversal" << endl;<br>
      cout << "4.PreOrder traversal" << endl;<br>
      cout << "5.PostOrder traversal" << endl;<br>
      cout << "6.Exit" << endl;<br>
      cout << "Enter your Choice: ";<br>
      cin >> c;<br>
      switch (c) {<br>
         case 1:<br>
            cout << "Enter value to be inserted: ";<br>
            cin >> i;<br>
            r = avl.insert(r, i);<br>
         break;<br>
         case 2:<br>
            if (r == NULL) {<br>
               cout << "Tree is Empty" << endl;<br>
               continue;<br>
            }<br>
            cout << "Balanced AVL Tree:" << endl;<br>
            avl.show(r, 1);<br>
            cout<<endl;<br>
         break;<br>
         case 3:<br>
            cout << "Inorder Traversal:" << endl;<br>
            avl.inorder(r);<br>
            cout << endl;<br>
         break;<br>
         case 4:<br>
            cout << "Preorder Traversal:" << endl;<br>
            avl.preorder(r);<br>
            cout << endl;<br>
         break;<br>
         case 5:<br>
            cout << "Postorder Traversal:" << endl;<br>
            avl.postorder(r);<br>
            cout << endl;<br>
         break;<br>
         case 6:<br>
            exit(1);<br>
         break;<br>
         default:<br>
            cout << "Wrong Choice" << endl;<br>
      }<br>
   }<br>
   return 0;<br>
}<br>
**output:**<br>
![image](https://user-images.githubusercontent.com/98145574/159209156-b6d095c5-ba8b-453f-86d7-f01e5a613780.png)<br><br>
Enter value to be inserted: 9<br>
Right-Right Rotation1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 1<br>
Enter value to be inserted: 10<br>
Right-Right Rotation1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 1<br>
Enter value to be inserted: 11<br>
Right-Right Rotation1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 2<br>
Balanced AVL Tree:<br>
    11   10    9 Root -> 6    5   3    2<br>
1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 3<br>
Inorder Traversal:<br>
2 3 5 6 9 10 11<br>
1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 4<br>
Preorder Traversal:<br>
6 3 2 5 10 9 11<br>
1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 5<br>
Postorder Traversal:<br>
2 5 3 9 11 10 6<br>
1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 6<br>
--------------------------------<br>

**9.Merge Sort using Divide and encounter method.<br>**
#include<bits/stdc++.h><br>
using namespace std;<br>
void mergeofarrays(int a[],int low,int mid,int high)<br>
    {<br>
     int i=low,j=mid+1,index=low,temp[100],k;<br>
      while((i<=mid)&&(j<=high))<br>
      {<br>
        if(a[i]<a[j])<br>
        {<br>
        temp[index]=a[i];<br>
        i++;<br>
        }<br>
        else<br>
        {<br>
            temp[index]=a[j];<br>
            j++;<br>
        }<br>
        index++;<br>
      }<br>
        if(i>mid)<br>
        {<br>
            while(j<=high)<br>
            {<br>
                temp[index]=a[j];<br>
                j++;<br>
                index++;<br>
            }<br>
        }<br>
         else<br>
        {<br>
            while(i<=mid)<br>
          {<br>
            temp[index]=a[i];<br>
            i++;<br>
            index++;<br>
          }<br>
        }<br>
        for(k=low;k<index;k++)<br>
        {<br>
            a[k]=temp[k];<br>
        }<br>
    }<br>
        void mergesort(int a[], int low, int high)<br>
        {<br>
            if(low<high)<br>
            {<br>
                int middle=(low+high)/2;<br>
                mergesort(a,low,middle);<br>
                mergesort(a,middle+1,high);<br>
                mergeofarrays(a,low,middle,high);<br>
            }<br>
        }<br>
        int main()<br>
        {<br>
            int n=7;<br>
            int a[100]={54,34,23,10,98,2,3};<br>
            mergesort(a,0,6);<br>
            for(int i=0;i<n;i++)<br>
            {<br>
                cout<<a[i]<<" ";<br>
            }<br>
        }<br>

**output:<br>**	
  ![image](https://user-images.githubusercontent.com/98145574/162893226-a31aaac9-c413-4c0c-b348-7c472194279b.png)<br>
	
**10.Write a C++ program for solving N-Queen’s problem using Backtracking.**<br>
#include<iostream><br>
using namespace std;<br>
int grid[10][10];

void print(int n) {<br>
    for (int i = 0;i <= n-1; i++) {<br>
        for (int j = 0;j <= n-1; j++) {<br>
            
                cout <<grid[i][j]<< " ";<br>
            
        }<br>
        cout<<endl;<br>
    }<br>
    cout<<endl;<br>
    cout<<endl;<br>
}<br>
bool isSafe(int col, int row, int n) {<br>
    for (int i = 0; i < row; i++) {<br>
        if (grid[i][col]) {<br>
            return false;<br>
        }<br>
    }<br>
    for (int i = row,j = col;i >= 0 && j >= 0; i--,j--) {<br>
        if (grid[i][j]) {<br>
            return false;<br>
        }<br>
    }<br>
    for (int i = row, j = col; i >= 0 && j < n; j++, i--) {<br>
        if (grid[i][j]) {<br>
            return false;<br>
        }<br>
    }<br>
    return true;<br>
}<br>
bool solve (int n, int row) {<br>
    if (n == row) {<br>
        print(n);<br>
        return true;<br>
    }<br>
    bool res = false;<br>
    for (int i = 0;i <=n-1;i++) {<br>
        if (isSafe(i, row, n)) {<br>
            grid[row][i] = 1;<br>
            res = solve(n, row+1) || res;//if res ==false then backtracking will occur <br>
            grid[row][i] = 0;<br>
        }<br>
    }<br>
    return res;<br>
}<br>
int main()<br>
{<br>
  ios_base::sync_with_stdio(false);<br>
    cin.tie(NULL);<br>
        int n;<br>
        cout<<"Enter the number of queen"<<endl;<br>
        cin >> n;<br>
        for (int i = 0;i < n;i++) {<br>
            for (int j = 0;j < n;j++) {<br>
                grid[i][j] = 0;<br>
            }<br>
        }<br>
        bool res = solve(n, 0);<br>
        if(res == false) {<br>
            cout <<" solution not found ";<br>
			<< endl; //if there is no possible solution<br>
        } else {<br>
            cout << endl;<br>
        }<br>
  return 0;<br>
}<br>
**output:**<br>
	![image](https://user-images.githubusercontent.com/98145574/163937813-efed0744-98b2-4c1d-9125-3d8fc4b2e39a.png)<br>
11.
#include<iostream><br>
#include<vector><br>
#include<queue><br>
#include<stack><br>
using namespace std;<br>
void edge(vector<int>adj[],int u,int v){<br>
  adj[u].push_back(v);<br>
}<br>
void bfs(int s,vector<int>adj[],bool visit[]){<br>
  queue<int>q;<br>
  q.push(s);<br>
  visit[s]=true;<br>
  while(!q.empty()){<br>
    int u=q.front();<br>
    cout<<u<<" ";<br>
    q.pop();<br>
    for(int i=0;i<adj[u].size();i++){<br>
      if(!visit[adj[u][i]]){<br>
        q.push(adj[u][i]);<br>
        visit[adj[u][i]]=true;<br>
      }<br>
    }<br>
  }<br>
}<br>
void dfs(int s,vector<int>adj[],bool visit[]){<br>
  stack<int>stk;<br>
  stk.push(s);<br>
  visit[s]=true;<br>
  while(!stk.empty()){<br>
    int u=stk.top();<br>
    cout<<u<<" ";<br>
    stk.pop();<br>
    for(int i=0;i<adj[u].size();i++){<br>
      if(!visit[adj[u][i]]){<br>
        stk.push(adj[u][i]);<br>
        visit[adj[u][i]]=true;<br>
      }<br>
    }<br>
  }<br>
}<br>
int main(){<br>
  vector<int>adj[5];<br>
  bool visit[5];<br>
  for(int i=0;i<5;i++){<br>
    visit[i]=false;<br>
  }<br>
  edge(adj,0,2);<br>
  edge(adj,0,1);<br>
  edge(adj,1,3);<br>
  edge(adj,2,0);<br>
  edge(adj,2,3);<br>
  edge(adj,2,4);<br>
  cout<<"BFS traversal is"<<"  ";<br>
  bfs(0,adj,visit);<br>
  cout<<endl;<br>
  for(int i=0;i<5;i++){<br>
    visit[i]=false;<br>
  }<br>
  cout<<"DFS traversal is"<<"  ";<br>
  dfs(0,adj,visit);<br>
}<br>
	![image](https://user-images.githubusercontent.com/98145574/163942802-c64c81c2-ca49-4112-ab36-d46cea028473.png)<br>


 https://www.iare.ac.in/sites/default/files/DAA%20%20Notes%20by%20Dr.%20L.%20V.%20Narasimha%20Prasad_0.pdf

