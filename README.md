# Stack and Circular Queue Implementation

This repository contains implementations and analysis of Stack and Circular Queue using fixed-size arrays.

---

## Question 1: Stack using Array

### Python Implementation

```python
class Stack:
    def __init__(self, capacity):
        self.capacity = capacity
        self.stack = [None] * capacity
        self.top = -1  # Tracks top element

    def push(self, x):
        if self.top == self.capacity - 1:
            print(f"Stack Overflow! Cannot push {x}.")
            return
        self.top += 1
        self.stack[self.top] = x
        print(f"Pushed {x}")

    def pop(self):
        if self.top == -1:
            print("Stack Underflow!")
            return None
        popped_val = self.stack[self.top]
        self.top -= 1
        print(f"Popped {popped_val}")
        return popped_val

    def peek(self):
        if self.top == -1:
            print("Stack is empty.")
            return None
        print(f"Top element: {self.stack[self.top]}")
        return self.stack[self.top]

    def display(self):
        if self.top == -1:
            print("Stack is empty.")
            return
        print("Stack elements:", self.stack[self.top::-1])

