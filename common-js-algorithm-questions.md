1. Reverse a string:

```javascript
function reverseString(str) {
  return str.split("").reverse().join("");
}

const reversed = reverseString("hello");
console.log(reversed); // Output: 'olleh'
```

Explanation: The `reverseString` function splits the string into an array of characters using `split('')`, reverses the order of the characters using `reverse()`, and then joins them back into a string using `join('')`. This effectively reverses the original string.

2. Find the largest number in an array:

```javascript
function findLargestNumber(arr) {
  return Math.max(...arr);
}

const numbers = [5, 2, 9, 1, 7];
const largest = findLargestNumber(numbers);
console.log(largest); // Output: 9
```

Explanation: The `findLargestNumber` function uses the spread operator (`...`) to pass the array elements as individual arguments to the `Math.max` function. This returns the largest number in the array.

3. Check for Palindrome:

```javascript
function isPalindrome(str) {
  const reversed = str.split("").reverse().join("");
  return str === reversed;
}

const isPalindrome = isPalindrome("racecar");
console.log(isPalindrome); // Output: true
```

Explanation: The `isPalindrome` function splits the string into an array of characters, reverses the order, and joins them back into a string. It then compares the original string with the reversed string to determine if it is a palindrome.

4. Find the factorial of a number:

```javascript
function factorial(n) {
  if (n === 0 || n === 1) {
    return 1;
  }
  return n * factorial(n - 1);
}

const result = factorial(5);
console.log(result); // Output: 120
```

Explanation: The `factorial` function uses recursion to calculate the factorial of a number. It checks if the number is 0 or 1 (base case) and returns 1. Otherwise, it multiplies the number by the factorial of (n - 1) until the base case is reached.

5. Remove duplicates from an array:

```javascript
function removeDuplicates(arr) {
  return [...new Set(arr)];
}

const numbers = [1, 2, 3, 2, 4, 1];
const uniqueNumbers = removeDuplicates(numbers);
console.log(uniqueNumbers); // Output: [1, 2, 3, 4]
```

Explanation: The `removeDuplicates` function converts the array into a Set, which automatically removes duplicate values. Then, it spreads the Set back into an array using the spread operator to obtain an array with unique values.

6. Implement a binary search:

```javascript
function binarySearch(arr, target) {
  let left = 0;
  let right = arr.length - 1;

  while (left <= right) {
    let mid = Math.floor((left + right) / 2);

    if (arr[mid] === target) {
      return mid;
    } else if (arr[mid] < target) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }

  return -1;
}

const numbers = [2, 4, 6, 8, 10];
const targetIndex = binarySearch(numbers, 8);
console.log(targetIndex); // Output: 3
```

Explanation: The `binarySearch` function implements the binary search algorithm. It maintains two

pointers, `left` and `right`, which represent the range of the array to search. It repeatedly calculates the middle index (`mid`) and compares the target value with the middle element. If they are equal, it returns the index. If the target is smaller, it narrows the search range by moving `right` to `mid - 1`. If the target is larger, it narrows the range by moving `left` to `mid + 1`. The loop continues until the target is found or the range is empty.

7. Check for balanced parentheses:

```javascript
function isBalanced(str) {
  const stack = [];

  for (let char of str) {
    if (char === "(" || char === "[" || char === "{") {
      stack.push(char);
    } else if (char === ")" && stack[stack.length - 1] === "(") {
      stack.pop();
    } else if (char === "]" && stack[stack.length - 1] === "[") {
      stack.pop();
    } else if (char === "}" && stack[stack.length - 1] === "{") {
      stack.pop();
    } else {
      return false;
    }
  }

  return stack.length === 0;
}

const parentheses = "((()))";
const isBalanced = isBalanced(parentheses);
console.log(isBalanced); // Output: true
```

Explanation: The `isBalanced` function uses a stack data structure to check for balanced parentheses. It iterates through each character in the string and pushes opening parentheses onto the stack. When it encounters a closing parenthesis, it checks if it matches the top element of the stack (the corresponding opening parenthesis). If they match, it pops the opening parenthesis from the stack. If they don't match or if the stack is empty, it returns false. Finally, it checks if the stack is empty at the end to determine if all parentheses are balanced.

8. Find the second largest number in an array:

```javascript
function findSecondLargest(arr) {
  let max = -Infinity;
  let secondMax = -Infinity;

  for (let num of arr) {
    if (num > max) {
      secondMax = max;
      max = num;
    } else if (num > secondMax && num < max) {
      secondMax = num;
    }
  }

  return secondMax;
}

const numbers = [5, 2, 9, 1, 7];
const secondLargest = findSecondLargest(numbers);
console.log(secondLargest); // Output: 7
```

Explanation: The `findSecondLargest` function iterates through each number in the array. It keeps track of the maximum number (`max`) and the second maximum number (`secondMax`). If a number is greater than `max`, it updates both `max` and `secondMax`. If a number is greater than `secondMax` but less than `max`, it only updates `secondMax`. Finally, it returns `secondMax`, which will be the second largest number in the array.

9. Check if two strings are anagrams:

```javascript
function isAnagram(str1, str2) {
  const sortedStr1 = str1.toLowerCase().split("").sort().join("");
  const sortedStr2 = str2.toLowerCase().split("").sort().join("");
  return sortedStr1 === sortedStr2;
}

const word1 = "listen";
const word2 = "silent";
const isAnagram = isAnagram(word1, word2);
console.log(isAnagram); // Output: true
```

Explanation: The `isAnagram` function converts both strings to lowercase, splits them into arrays of characters,

sorts the arrays, and joins them back into strings. Then, it compares the sorted strings to check if they are equal. If they are equal, the two strings are anagrams.

10. Reverse words in a string:

```javascript
function reverseWords(str) {
  return str.split(" ").reverse().join(" ");
}

const sentence = "Hello world";
const reversedWords = reverseWords(sentence);
console.log(reversedWords); // Output: 'world Hello'
```

Explanation: The `reverseWords` function splits the string into an array of words using the space character as the delimiter. It then reverses the order of the words using `reverse()` and joins them back into a string using the space character as the separator.

11. Find the sum of all numbers in an array:

```javascript
function sumArray(arr) {
  return arr.reduce((sum, num) => sum + num, 0);
}

const numbers = [1, 2, 3, 4, 5];
const sum = sumArray(numbers);
console.log(sum); // Output: 15
```

Explanation: The `sumArray` function uses the `reduce` method to iterate through the array and accumulate the sum of all numbers. It initializes the accumulator (`sum`) to 0 and adds each number to it.

12. Find the first non-repeating character in a string:

```javascript
function findFirstNonRepeatingChar(str) {
  const charCount = {};

  for (let char of str) {
    charCount[char] = (charCount[char] || 0) + 1;
  }

  for (let char of str) {
    if (charCount[char] === 1) {
      return char;
    }
  }

  return null;
}

const word = "abracadabra";
const firstNonRepeatingChar = findFirstNonRepeatingChar(word);
console.log(firstNonRepeatingChar); // Output: 'c'
```

Explanation: The `findFirstNonRepeatingChar` function uses an object (`charCount`) to store the count of each character in the string. It iterates through the string and updates the count for each character. Then, it iterates through the string again and returns the first character with a count of 1.

13. Find the maximum sum of a subarray:

```javascript
function findMaxSubarraySum(arr) {
  let maxSum = arr[0];
  let currentSum = arr[0];

  for (let i = 1; i < arr.length; i++) {
    currentSum = Math.max(arr[i], currentSum + arr[i]);
    maxSum = Math.max(maxSum, currentSum);
  }

  return maxSum;
}

const numbers = [-2, 3, -1, 4, -2, 1, 5, -3];
const maxSum = findMaxSubarraySum(numbers);
console.log(maxSum); // Output: 10
```

Explanation: The `findMaxSubarraySum` function uses the Kadane's algorithm to find the maximum sum of a subarray. It maintains two variables: `maxSum` to track the maximum sum encountered so far, and `currentSum` to track the current sum of the subarray. It iterates through the array, updating `currentSum` by either taking the current element or adding it to the current sum. It also updates `maxSum` whenever a new maximum sum is found.

14. Check if a string is a palindrome (ignoring non-alphanumeric characters):

```javascript
function isPalindrome(str) {
  const alphanumericStr = str.toLowerCase().replace(/[^a-z0-9]/g, "");
  const reversedStr = alphanumericStr.split("").reverse().join("");
  return alphanumericStr === reversedStr;
}

const sentence = "A man, a plan, a canal: Panama!";
const isPalindrome = isPalindrome(sentence);
console.log(isPalindrome); // Output: true
```

Explanation: The `isPalindrome` function converts the string to lowercase, removes all non-alphanumeric characters using a regular expression, and then checks if the resulting alphanumeric string is equal to its reversed version.

15. Find the missing number in an array:

```javascript
function findMissingNumber(arr) {
  const n = arr.length + 1;
  const expectedSum = (n * (n + 1)) / 2;
  const actualSum = arr.reduce((sum, num) => sum + num, 0);
  return expectedSum - actualSum;
}

const numbers = [1, 2, 4, 5];
const missingNumber = findMissingNumber(numbers);
console.log(missingNumber); // Output: 3
```

Explanation: The `findMissingNumber` function uses the formula for the sum of consecutive integers to calculate the expected sum of the array if it contained all numbers from 1 to n. It then calculates the actual sum of the given array using the `reduce` method. Subtracting the actual sum from the expected sum gives the missing number.

16. Remove duplicates from a sorted array in-place:

```javascript
function removeDuplicates(nums) {
  let i = 0;

  for (let j = 1; j < nums.length; j++) {
    if (nums[j] !== nums[i]) {
      i++;
      nums[i] = nums[j];
    }
  }

  return i + 1;
}

const numbers = [1, 1, 2, 2, 3, 4, 5, 5];
const length = removeDuplicates(numbers);
console.log(numbers.slice(0, length)); // Output: [1, 2, 3, 4, 5]
```

Explanation: The `removeDuplicates` function uses two pointers, `i` and `j`, to iterate through the array. It compares the element at `j` with the element at `i`. If they are different, it increments `i`, assigns the value at `j` to `nums[i]`, and effectively moves the unique element to the next position in the array. Finally, it returns `i + 1`, which represents the length of the array without duplicates.

17. Find the longest substring without repeating characters:

```javascript
function findLongestSubstring(str) {
  let longest = 0;
  let start = 0;
  const charMap = {};

  for (let i = 0; i < str.length; i++) {
    const char = str[i];
    if (charMap[char] >= start) {
      start = charMap[char] + 1;
    }
    charMap[char] = i;
    longest = Math.max(longest, i - start + 1);
  }

  return longest;
}

const word = "abcabcbb";
const length = findLongestSubstring(word);
console.log(length); // Output: 3
```

Explanation: The `findLongestSubstring` function uses the sliding window technique to find the longest substring without repeating characters. It maintains a `start` index to track the start of the current substring and a `charMap` object to store the most recent index of each character. When a repeated character is encountered, the `start` index is updated to the next position after the last occurrence of that character. The length of the substring is calculated at each step and the maximum length is stored in `longest`.

18. Check if a number is prime

:

```javascript
function isPrime(num) {
  if (num <= 1) {
    return false;
  }

  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) {
      return false;
    }
  }

  return true;
}

const number = 17;
const isPrimeNumber = isPrime(number);
console.log(isPrimeNumber); // Output: true
```

Explanation: The `isPrime` function checks if a number is prime by iterating from 2 up to the square root of the number. If any divisor is found, the number is not prime. If no divisor is found, the number is prime. It also handles special cases where the number is less than or equal to 1, considering them as non-prime.

19. Implement a queue using two stacks:

```javascript
class Queue {
  constructor() {
    this.stack1 = [];
    this.stack2 = [];
  }

  enqueue(value) {
    while (this.stack1.length) {
      this.stack2.push(this.stack1.pop());
    }
    this.stack1.push(value);
    while (this.stack2.length) {
      this.stack1.push(this.stack2.pop());
    }
  }

  dequeue() {
    return this.stack1.pop();
  }

  peek() {
    return this.stack1[this.stack1.length - 1];
  }

  isEmpty() {
    return this.stack1.length === 0;
  }
}

const queue = new Queue();
queue.enqueue(1);
queue.enqueue(2);
queue.enqueue(3);
console.log(queue.dequeue()); // Output: 1
console.log(queue.peek()); // Output: 2
console.log(queue.isEmpty()); // Output: false
```

Explanation: The `Queue` class implements a queue data structure using two stacks. The `enqueue` method first transfers all elements from `stack1` to `stack2`, pushes the new value onto `stack1`, and transfers the elements back from `stack2` to `stack1`. This ensures that the newest element is always at the bottom of `stack1`, simulating a queue. The `dequeue` method simply pops the top element from `stack1`. The `peek` method returns the top element of `stack1` without removing it. The `isEmpty` method checks if `stack1` is empty.

20. Find the number of occurrences of a target value in a sorted array:

```javascript
function countOccurrences(arr, target) {
  function findFirstOccurrence() {
    let left = 0;
    let right = arr.length - 1;
    let index = -1;

    while (left <= right) {
      let mid = Math.floor((left + right) / 2);

      if (arr[mid] === target) {
        index = mid;
        right = mid - 1;
      } else if (arr[mid] < target) {
        left = mid + 1;
      } else {
        right = mid - 1;
      }
    }

    return index;
  }

  function findLastOccurrence() {
    let left = 0;
    let right = arr.length - 1;
    let index = -1;

    while (left <= right) {
      let mid = Math.floor((left + right) / 2);

      if (arr[mid] === target) {
        index = mid;
        left = mid + 1;
      } else if (arr[mid] < target) {
        left = mid + 1;
      } else {
        right = mid - 1;
      }
    }

    return index;
  }

  const firstOccurrence = findFirstOccurrence();
  const lastOccurrence = findLastOccurrence();

  if (firstOccurrence !== -1 && lastOccurrence !== -1) {
    return lastOccurrence - firstOccurrence + 1;
  }

  return 0;
}

const numbers = [1, 2, 2, 2, 3, 4, 5, 5];
const target = 2;
const occurrences = countOccurrences(numbers, target);
console.log(occurrences); // Output: 3
```

Explanation: The `countOccurrences` function uses two helper functions, `findFirstOccurrence` and `findLastOccurrence`, to find the first and last occurrence of the target value in the sorted array using the binary search algorithm. It then calculates the number of occurrences by subtracting the first occurrence index from the last occurrence index and adding 1. If either the first or last occurrence is not found, it returns 0.
