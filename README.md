# Experiment 18

## Aim:
To explore and implement Stack using arrays.

## Apparatus:
VS Code, GitHub

## Theory:

A stack is a linear data structure that operates based on the Last In, First Out (LIFO) method. This implies that the last item added to the stack is the first one to be removed. In C++, stacks can be implemented either with arrays or linked lists. For this program, we will use an array to implement the stack. In this implementation, the stack is represented by the array `stack[]`.

### Basic operations:
1: Push: Inserts an element onto the top of the stack.  
   Before inserting, check if the stack is full (`top == max - 1`), where `max` is the maximum size of the stack.  
   If it’s not full, increment `top` and add the new element at `stack[top]`.

2: Pop: Removes the top element from the stack.  
   Before removing, check if the stack is empty (`top == -1`).  
   If it’s not empty, remove the element from `stack[top]` and decrement `top`.

3: Peek/Top: Retrieves the top element without removing it.  
   Access the element at `stack[top]` without changing `top`.  
   Before doing this, ensure that the stack is not empty.

## Explanation:

### Class Definition (Stack):
The `Stack` class contains the stack attributes and operations.  
An array `arr[size]` is used to store the elements of the stack, while an integer `top` keeps track of the index of the top element.

### Constructor (Stack()):
Initializes `top` to -1, indicating that the stack is initially empty.

### Push Method (push(int value)):
Verifies if the stack is full, and if so, displays an error message.  
Otherwise, it increments `top` and stores the value in `arr[top]`.

### Pop Method (pop()):
Checks if the stack is empty. If it is, an error message is shown.  
Otherwise, it decrements `top`, effectively removing the top element.

### Peek Method (peek()):
Returns the value at `arr[top]` without removing it.  
If the stack is empty, it returns an error value.

## Code:

### Stack using array:
```cpp
#include<iostream>
using namespace std;
#define size 5
#define ERROR -9999

class Stack{
    int top, ar[size];
    public:
    Stack(){
        top=-1;
        ar[0]=0;
    }
    void push(int);
    int pop();
    int peak();
    void disp();
};
void Stack::push(int num){
    if(top==size-1){
        cout<<"STACK OVERFLOW: Stack is full"<<endl;
        return;
    }
    else{
        ar[++top]=num;
    }
}
int Stack::pop(){
    int val;
    if(top==-1){
        cout<<"STACK UNDERFLOW: Stack is empty"<<endl;
        return ERROR;
    }
    else{
        val=ar[top--];
        return val;
    }
}
int Stack::peak(){
    if(top==-1){
        cout<<"STACK UNDERFLOW: Stack is empty"<<endl;
        return ERROR;
    }
    else{
        return ar[top];
    }
}
void Stack::disp(){
    if(top==-1){
        cout<<"STACK UNDERFLOW: Stack is empty"<<endl;
        return;
    }
    else{
        int i=0;
        while(i!=(top+1)){
            cout<<ar[i]<<"  ";
            i++;
        }

    }
}

int main(){
    Stack s1;
    s1.push(7);
    s1.push(10);
    s1.push(4);
    int val=s1.pop();
    cout<<val<<endl;
    int top=s1.peak();
    cout<<top<<endl;
    s1.disp();
    return 0;
}
```
### Output:
![image_2024-10-21_141955448](https://github.com/user-attachments/assets/67bc44ef-52ea-4f24-922e-6ec528e360a8)


## Conclusion:
This program helps us understand how stacks can be implemented using arrays. We learnt the different commands/keywords used in stacks such as push, pop and peek.
