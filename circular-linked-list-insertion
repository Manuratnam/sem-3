#include <iostream>
using namespace std;

// 1. Define the node just like the image (but without the class)
struct node 
{
    int data;            //[span_3](start_span)[span_3](end_span)
    struct node *link;   //[span_4](start_span)[span_4](end_span)
};

// Global tracking pointers from the image
struct node *tail = NULL;    //[span_5](start_span)[span_5](end_span)
struct node *newnode = NULL; //[span_6](start_span)[span_6](end_span)
struct node *temp = NULL;    //[span_7](start_span)[span_7](end_span)

// 2. Function to add a node to the end of the circle
void insertend(int num)      //[span_8](start_span)[span_8](end_span)
{
    // Create the new node
    newnode = new node;
    newnode->data = num;
    newnode->link = NULL;

    if (tail == NULL) 
    {
        // If the list is empty, this single node forms a circle with itself!
        tail = newnode;
        tail->link = tail; // It points to itself
    } 
    else 
    {
        // Add the new node to the circle
        newnode->link = tail->link; // 1. New node points to the first node
        tail->link = newnode;       // 2. Old last node points to the new node
        tail = newnode;             // 3. The new node becomes the official tail
    }
}

// 3. Function to print the circle
void display()               //[span_9](start_span)[span_9](end_span)
{
    if (tail == NULL) 
    {
        cout << "List is empty.\n";
    } 
    else 
    {
        // Start at the first node (which is tail->link)
        temp = tail->link;
        
        cout << "Circular Linked List: ";
        
        // We use a do-while loop because we need it to run until it circles back
        do 
        {
            cout << temp->data << " -> ";
            temp = temp->link;             // Move to the next node
            
        } while (temp != tail->link);      // Stop when we reach the first node again
        
        cout << "(back to start)\n";
    }
}

// 4. Main program to run it
int main() 
{
    // Add numbers to our circular list
    insertend(10);
    insertend(20);
    insertend(30);

    // Print the list to the screen
    display();

    return 0;
}
