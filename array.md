<div align="center">
  <img height="60" src="https://img.icons8.com/color/344/javascript.png">
  <h1>JavaScript Questions</h1>
</div>

> [!NOTE]  
> This repo was created in 2019 and the questions provided here are therefore based on the JavaScript syntax and behavior at that time. Since JavaScript is a constantly evolving language, there are newer language features that are not covered by the questions here.

---
---

###### 1. What's the output?

```javascript
const arr = [];
arr.length = 3;
arr[2] = 1;
arr.forEach((el, i) => console.log(i))

```

<!-- - A: `Lydia` and `undefined`
- B: `Lydia` and `ReferenceError`
- C: `ReferenceError` and `21`
- D: `undefined` and `ReferenceError` -->

<details><summary><b>Answer</b></summary>
<p>

#### Answer: 2

<!-- Within the function, we first declare the `name` variable with the `var` keyword. This means that the variable gets hoisted (memory space is set up during the creation phase) with the default value of `undefined`, until we actually get to the line where we define the variable. We haven't defined the variable yet on the line where we try to log the `name` variable, so it still holds the value of `undefined`.

Variables with the `let` keyword (and `const`) are hoisted, but unlike `var`, don't get <i>initialized</i>. They are not accessible before the line we declare (initialize) them. This is called the "temporal dead zone". When we try to access the variables before they are declared, JavaScript throws a `ReferenceError`. -->

Explanation:

1.	Array Initialization:
o	const arr = []; creates an empty array arr.
2.	Setting Array Length:
o	arr.length = 3; sets the length of the array to 3.
o	This creates an array with 3 slots, but since you haven't explicitly set values for the elements at indices 0 and 1, they are "empty" (not undefined, but actually uninitialized).
3.	Setting a Specific Element:
o	arr[2] = 1; assigns the value 1 to the element at index 2.
At this point, the array arr looks like this:
javascript
Copy code
[empty × 2, 1]
4.	forEach Loop:
o	arr.forEach((el, i) => console.log(i)); iterates over the array and logs the index of each element to the console.
o	The forEach method only iterates over elements that are explicitly set in the array. It skips any "empty" slots.
o	In this case, it will only iterate over the element at index 2, since it's the only one that has been assigned a value.
Output:
The code will output:
Copy code
2
Key Points:
•	The forEach method skips uninitialized (empty) slots in the array.
•	Since arr[2] is the only initialized element, forEach only logs the index 2.•	

</p>
</details>

---

###### 2. What's the output?

```javascript
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1);
}

for (let i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1);
}
```

- A: `0 1 2` and `0 1 2`
- B: `0 1 2` and `3 3 3`
- C: `3 3 3` and `0 1 2`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

Because of the event queue in JavaScript, the `setTimeout` callback function is called _after_ the loop has been executed. Since the variable `i` in the first loop was declared using the `var` keyword, this value was global. During the loop, we incremented the value of `i` by `1` each time, using the unary operator `++`. By the time the `setTimeout` callback function was invoked, `i` was equal to `3` in the first example.

In the second loop, the variable `i` was declared using the `let` keyword: variables declared with the `let` (and `const`) keyword are block-scoped (a block is anything between `{ }`). During each iteration, `i` will have a new value, and each value is scoped inside the loop.

</p>
</details>

---