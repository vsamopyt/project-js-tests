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
const a = [1, 2, 3];
const b = a;
b[0] = 0;

console.log(a);
```

<details><summary><b>Answer</b></summary>
<p>

#### Answer: [0,2,3]

because of reference link

</p>
</details>

---

###### 3. What's the output?

```javascript
const array = [];
array[10] =10; 
console.log(array.length);
```

<details><summary><b>Answer</b></summary>
<p>

#### Answer: 11

because of

</p>
</details>

---

###### 4. What's the output?

```javascript
const array_1 =new Array(1,2,3);
const array_2 = new Array(3);
console.log(array_1.length, array_2.length);
console.log(array_1[0]+array_2[0]);
console.log(array_2[0]);
```

<details><summary><b>Answer</b></summary>
<p>

#### Answer: 3,3 NaN, undefined

because of

</p>
</details>

---

###### 4. What's the output?

```javascript
const numbers =[1,2,3,4,5];
const a = numbers;
const [b] = numbers
const [c,d]= numbers;

console.log(a,b,c,d);
```

<!-- - A: `0 1 2` and `0 1 2`
- B: `0 1 2` and `3 3 3`
- C: `3 3 3` and `0 1 2` -->

<details><summary><b>Answer</b></summary>
<p>

#### Answer: [1, 2, 3, 4, 5], 1, 1 2

beacuse of 

</p>
</details>

---

###### 5. What's the output?

```javascript
const toDoList = (array) => {
    return array.push(5);
}
const list = [1,2,3];
const result = toDoList(list);

console.log(result);
console.log(list);
```

<details><summary><b>Answer</b></summary>
<p>

#### Answer: 4, [1,2,3,4]

beacuse of

</p>
</details>

---

###### 6. What's the output?

```javascript
const toDoList =(value, list)=> {
    return list.push(value);
}
let b= toDoList(4, [1,1]);
console.log(b);
```

<!-- - A: `0 1 2` and `0 1 2`
- B: `0 1 2` and `3 3 3`
- C: `3 3 3` and `0 1 2` -->

<details><summary><b>Answer</b></summary>
<p>

#### Answer: 3

 beacuse of

</p>
</details>

---

###### 6. What's the output?

```javascript
const a = [1,2].push(10);
console.log(a.push(20))
```

<!-- - A: `0 1 2` and `0 1 2`
- B: `0 1 2` and `3 3 3`
- C: `3 3 3` and `0 1 2` -->

<details><summary><b>Answer</b></summary>
<p>

#### Answer: typeError

 beacuse of

</p>
</details>

---

###### 7. What's the output?

```javascript
let arr = [];
console.log(fillArray(2, 10));
function fillArray(min, max) {
  for (let i = min; i <= max; i += 2) {
    return arr.push(i);
  }
}
```


<details><summary><b>Answer</b></summary>
<p>

#### Answer: 1

 In your current code, the fillArray function will return after the first iteration of the loop due to the return statement inside the loop. This means that the function will stop running after it pushes the first even number (2 in this case) to the array, and it will return the result of the arr.push(i) operation.

The arr.push(i) method adds an element to the array and returns the new length of the array (which will be 1 after the first push).

So, the result of calling fillArray(2, 10) in this case will be 1, since the array will contain only one element (2) and the push method will return the new length of the array.

Here’s what happens step-by-step:

i = 2 (the loop starts).
arr.push(i) adds 2 to the array, and arr becomes [2].
The function returns the result of arr.push(i), which is 1 (the new length of the array).
The loop stops because of the return statement.
So, the output of console.log(fillArray(2, 10)); will be 1, and the array arr will only contain [2].

</p>
</details>

---

###### 8. What's the output?

```javascript
let array = [1,2,3,4,5,6];
const a = array.splice(2,1);
console.log(a,array);
```


<details><summary><b>Answer</b></summary>
<p>

#### Answer: [3], [1, 2, 4, 5, 6]

because of

</p>
</details>

---

###### 9. What's the output?

```javascript
let array = [1,2,3,4,5,6];
const a = array.splice(2,2);
console.log(a,array);
```


<details><summary><b>Answer</b></summary>
<p>

#### Answer: [3,4], [1, 2, 5, 6]

because of

</p>
</details>

---

###### 10. What's the output?

```javascript
let array = [1,2,3,4,5,6];
const a = array.splice(2,2,10,20);
console.log(a,array);
```


<details><summary><b>Answer</b></summary>
<p>

#### Answer: [3, 4],[1, 2, 10, 20, 5, 6]

because of

</p>
</details>

---

###### 11. What's the output?

```javascript
let array1 = [1,2,3,4,5,6];
let array2 = array1;
array2.push(10);
console.log(array1);
```


<details><summary><b>Answer</b></summary>
<p>

#### Answer: [1,2,3,4,5,6,10];

because of

</p>
</details>

---

###### 12. What's the output?

```javascript
const result = New Array (3).map(item => 0)
```


<details><summary><b>Answer</b></summary>
<p>

#### Answer: [empty, empty, empty]

because of

</p>
</details>

---

###### 13. What's the output?

```javascript
console.log(
  [1, , 3].map((x, index) => {
    console.log(`Visit ${index}`);
    return x * 2;
  }),
);
```


<details><summary><b>Answer</b></summary>
<p>

#### Answer:  Visit 0, Visit 2 [2, empty, 6], or [2, , 6]

1. Array Elements
The array is [1, , 3]. This means:
At index 0, there is the value 1.
At index 1, there is a hole (not undefined, but an actual empty spot).
At index 2, there is the value 3.
2. The map Function Behavior
The map function only processes defined elements in the array. Holes in a sparse array are skipped and are not passed to the callback function.
3. Step-by-step Execution
Iteration 1: For index 0, the value is 1.

Logs: Visit 0.
Returns 1 * 2 = 2.
Iteration 2: For index 1, there is a hole (i.e., no value). The map function skips this index without invoking the callback.

No log output for this index because the callback is not called.
Iteration 3: For index 2, the value is 3.

Logs: Visit 2.
Returns 3 * 2 = 6.

</p>
</details>

---

###### 14. What's the output?

```javascript
const result = [1, 2, 3].map(item => {});
```


<details><summary><b>Answer</b></summary>
<p>

#### Answer:  [undefined. Undefined. Undefined]

if so, the function returns nothing (i.e., undefined), because return without a value implicitly returns undefined.

</p>
</details>

---

###### 15. What's the output?

```javascript
const result = [1, 2, 3].map(item => { if (typeof item === "number") { return; } return item * 2; });
```


<details><summary><b>Answer</b></summary>
<p>

#### Answer:  [undefined. Undefined. Undefined]

if (typeof item === "number") { return; }: This condition checks if item is a number, and if so, the function returns nothing (i.e., undefined), because return without a value implicitly returns undefined.

</p>
</details>

---

###### 16. What's the output?

```javascript
function updateBlock(width, height, ...other) {
    console.log(width, height, ...other);
}
updateBlock(100, 200, "red", "blau");
```


<details><summary><b>Answer</b></summary>
<p>

#### Answer:  100,200, "red", "blau"

В параметрах у нас Рест опереатор а Консоль лог спред оператор

</p>
</details>

---