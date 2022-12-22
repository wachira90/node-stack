# node-stack
node stack

## LIFO

- push (add a new element to stack)
- pop (remove the top element)


## Implementation

- isEmpty (print if the stack is empty or not)
- length (print the number of elements in the stack)
- push (add a new element to stack)
- pop (get and remove the top element)
- printStack (print all elements in stack)

## stack class

````
// Stack class 
class Stack {
    // Array is used to implement stack 
    constructor() {
        this.stack = [];
    }
    // push function 
    push(element) {
        // push element into the stack
        this.stack.push(element);
    }
    // pop function 
    pop() {
        // return top most element in the stack 
        // and removes it from the stack 
        // Underflow if stack is empty 
        if (this.stack.length == 0)
            return "Underflow";
        return this.stack.pop();
    }
    // length function 
    length() {
        // return stack legth
        return this.stack.length;
    }
    // isEmpty function 
    isEmpty() {
        // return true if stack is empty 
        return this.stack.length == 0;
    }
    // printStack function
    printStack() {
        var stringBuilder = "";
        for (var item = 0; item < this.stack.length; item++)
            stringBuilder += `${item}:` + this.stack[item] + '\n';
        return stringBuilder;
    }
}
module.exports = Stack;
````

## Test the Stack Class

nano index.js

````
const Stack = require('./stack');
const assert = require('assert').strict;
// creating a new stack
var stack = new Stack();

// returns true 
console.log('**Check if the stack is empty')
console.log(stack.isEmpty());
assert.deepEqual(stack.isEmpty(), true)
// returns zero
console.log('**Check if the stack has zero length')
console.log(stack.length());  
assert.deepEqual(stack.length(), 0)
// returns Underflow 
console.log('**Pop from the empty stack')
console.log(stack.pop()); 
assert.deepEqual(stack.pop(), 'Underflow')
// Adding memory slots to the stack 
console.log('**Push 3 memory slots to the stack')
stack.push('0x0000'); 
stack.push('0x0001'); 
stack.push('0x0002'); 
console.log('stack length:'+stack.length()); 
assert.deepEqual(stack.length(), 3)
// Printing the stack
console.log(stack.printStack());
// pop the last memory slot
console.log('**Pop the last memory slot from the stack')
var memorySlot = stack.pop();
console.log(memorySlot);
assert.deepEqual(memorySlot, '0x0002')
console.log('stack length:'+stack.length());
assert.deepEqual(stack.length(), 2)
// Printing the stack
console.log(stack.printStack()); 
````

## result

node index.js

````
//console output
**Check if the stack is empty
true
**Check if the stack has zero length
0
**Pop from the empty stack
Underflow
**Push 3 memory slots to the stack
stack length:3
0:0x0000
1:0x0001
2:0x0002
**Pop the last memory slot from the stack
0x0002
stack length:2
0:0x0000
1:0x0001
````
