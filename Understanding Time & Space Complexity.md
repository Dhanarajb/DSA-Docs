**# Understanding Time & Space Complexity (Day 1-2)**

## **1. Introduction to Time Complexity**
Time Complexity measures **how fast** an algorithm runs as the input size increases. It helps in comparing different approaches to solve a problem.

### **Why is Time Complexity Important?**
- Helps determine the efficiency of an algorithm.
- Avoids performance issues for large inputs.
- Used in coding interviews to judge problem-solving skills.

---

## **2. Big-O Notation**
Big-O Notation describes the **worst-case scenario** of an algorithm's time complexity. It tells how the execution time **scales** with input size.

### **Common Time Complexities**
| Notation | Complexity | Example |
|----------|-------------|-------------------------|
| O(1) | Constant | Accessing an array element `arr[i]` |
| O(log n) | Logarithmic | Binary search |
| O(n) | Linear | Looping through an array |
| O(n log n) | Linearithmic | Merge Sort, Quick Sort (average case) |
| O(n²) | Quadratic | Nested loops (Bubble Sort) |
| O(2^n) | Exponential | Recursion in Fibonacci |
| O(n!) | Factorial | Brute force in the Traveling Salesman Problem |

---

## **3. Understanding Each Complexity with Examples**

### **🔹 O(1) - Constant Time**
**Scenario:** Looking up a student's ID in a database with direct access.
```js
function getFirstElement(arr) {
    return arr[0]; // Always takes constant time
}
```
✅ No matter the size of `arr`, it takes the same time.

---

### **🔹 O(log n) - Logarithmic Time**
**Scenario:** Finding a word in a dictionary using **Binary Search**.
```js
function binarySearch(arr, target) {
    let left = 0, right = arr.length - 1;
    while (left <= right) {
        let mid = Math.floor((left + right) / 2);
        if (arr[mid] === target) return mid;
        if (arr[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return -1;
}
```
✅ Each step halves the search space, making it **logarithmic**.

---

### **🔹 O(n) - Linear Time**
**Scenario:** Checking if a name exists in a guest list.
```js
function findName(guestList, name) {
    for (let i = 0; i < guestList.length; i++) {
        if (guestList[i] === name) return true;
    }
    return false;
}
```
✅ Time grows linearly as input size increases.

---

### **🔹 O(n log n) - Linearithmic Time**
**Scenario:** Sorting a list of student marks.
```js
function mergeSort(arr) {
    if (arr.length <= 1) return arr;
    let mid = Math.floor(arr.length / 2);
    let left = mergeSort(arr.slice(0, mid));
    let right = mergeSort(arr.slice(mid));
    return merge(left, right);
}
```
✅ Efficient sorting algorithm used in real-world applications.

---

### **🔹 O(n²) - Quadratic Time**
**Scenario:** Comparing all students in a class to find duplicates.
```js
function hasDuplicates(arr) {
    for (let i = 0; i < arr.length; i++) {
        for (let j = i + 1; j < arr.length; j++) {
            if (arr[i] === arr[j]) return true;
        }
    }
    return false;
}
```
✅ Nested loops cause time complexity to grow quadratically.

---

## **4. Space Complexity**
Space Complexity measures how much **extra memory** an algorithm needs.

### **Common Space Complexities**
| Notation | Space Usage | Example |
|----------|------------|---------|
| O(1) | Constant | Swapping two variables |
| O(n) | Linear | Storing extra array |
| O(n²) | Quadratic | Storing a 2D matrix |

### **Example: O(1) vs O(n) Space Complexity**
```js
// O(1) Space Complexity
function swap(a, b) {
    let temp = a;
    a = b;
    b = temp;
}

// O(n) Space Complexity
function storeNumbers(n) {
    let arr = [];
    for (let i = 0; i < n; i++) {
        arr.push(i);
    }
    return arr;
}
```
✅ Using extra arrays increases space complexity.

---

## **5. Practice Problems**

**Q1:** What is the time complexity of this function?
```js
function printPairs(arr) {
    for (let i = 0; i < arr.length; i++) {
        for (let j = 0; j < arr.length; j++) {
            console.log(arr[i], arr[j]);
        }
    }
}
```
✅ Answer: **O(n²) (Quadratic Time)**

**Q2:** What is the space complexity of this function?
```js
function factorial(n) {
    if (n === 0) return 1;
    return n * factorial(n - 1);
}
```
✅ Answer: **O(n) (Recursive Stack Space)**

---

## **6. Summary**
- **Time Complexity** measures how execution time **scales** with input size.
- **Space Complexity** measures **extra memory usage**.
- **Big-O Notation** helps classify performance.
- **Optimizing time & space complexity is crucial in coding interviews.**

✅ **Next Step:** Start solving problems to strengthen understanding!

---

