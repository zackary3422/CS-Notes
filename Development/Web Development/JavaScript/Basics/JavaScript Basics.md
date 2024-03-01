

### **Introduction to JavaScript**

JavaScript is a high-level, interpreted programming language primarily used for adding interactivity and dynamic behavior to web pages. Basically adds logic to website

#### **Key Features**

- **Client-Side Scripting**: Executed on the client's browser.
  
- **Versatility**: Used for front-end and back-end development (Node.js).

### **Variables and Data Types**

JavaScript uses dynamic typing, allowing variables to hold different types of data.

#### **Variables**

- **Declaration**: `let`, `const`, `var` (older method due to no scope).
  
- **Example**:

```javascript
let age = 25; // Declaring a variable 'age' and assigning a value
const name = "John"; // Declaring a constant 'name' with a string value
```

#### **Data Types**

- **Primitive Types**: `number`, `string`, `boolean`, `null`, `undefined`, `symbol`.
  
- **Example**:

```javascript
let count = 10; // Number
let message = "Hello!"; // String
let isTrue = true; // Boolean
let nothing = null; // Null
let notDefined; // Undefined
```

### **Control Structures**

JavaScript provides various control structures for decision making and looping.

#### **Conditional Statements**

- **`if`, `else if`, `else`**:

```javascript
let num = 15;
if (num > 10) {
  console.log("Number is greater than 10");
} else if (num === 10) {
  console.log("Number is equal to 10");
} else {
  console.log("Number is less than 10");
}
```

#### **Loops**

- **`for`, `while`, `do-while`**:

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}

let x = 0;
while (x < 5) {
  console.log(x);
  x++;
}
```

### **Functions**

Functions in JavaScript allow code reusability and modularization.

#### **Function Declaration**

```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}

greet("Alice"); // Output: Hello, Alice!
```

#### **Arrow Functions (ES6+)**

```javascript
const add = (a, b) => a + b;

console.log(add(5, 3)); // Output: 8
```

### **Conclusion**

JavaScript is a versatile and powerful language used extensively in web development. Understanding its basics, including variables, data types, control structures, and functions, is crucial for building interactive and dynamic web applications.
