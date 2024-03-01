

### **Variables**

Variables in JavaScript are containers for storing data values. They follow certain rules for naming and can hold various types of data.

#### **Declaration**

Variables are declared using `let`, `const`, or `var` (outdate due to no scope).

```javascript
let age = 25; // Declaring a variable 'age' and assigning a value
const name = "John"; // Declaring a constant 'name' with a string value
var count = 10; // Declaring a variable 'count' using 'var'
```

#### **Naming Rules**

- Must begin with a letter, dollar sign ($), or underscore (_).
- Case-sensitive (`age`, `Age`, and `AGE` are different variables).

### **Data Types**

JavaScript has several primitive data types:

#### **Number**

Represents numeric values.

```javascript
let count = 10;
let price = 24.99;
```

#### **String**

Represents textual data, enclosed in single or double quotes.

```javascript
let message = "Hello, World!";
let name = 'Alice';
```

#### **Boolean**

Represents `true` or `false`.

```javascript
let isTrue = true;
let isFalse = false;
```

#### **Null**

Represents the absence of value.

```javascript
let nothing = null;
```

#### **Undefined**

Indicates a variable that has been declared but not assigned a value.

```javascript
let notDefined;
```

#### **Symbol** (ES6+)

Represents a unique identifier.

```javascript
let sym = Symbol('description');
```

### **Conclusion**

Understanding variables and data types in JavaScript is foundational. Variables store data values, while data types define the kind of data that can be stored and manipulated in the code.
