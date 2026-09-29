# Answers

## About You

1. **Introduce yourself.**
     I'm Hadhi Hassan, a full stack developer from Kerala, India, with about 1.3 years of experience building backend systems in Node.js, TypeScript and MongoDB most recently leading backend work on ERP platforms for a UAE-based company. I'm applying for the Node.js Backend Developer role.
2. **Do you own a personal computer?**
   Yes, Yes, I use it for all my development work.

3. **Describe your development environment. (Your OS, IDE, Editor and Config manager if any)**
  OS: Windows 11 , vscode and cursor

  ## Social Profile

1. **Your StackOverflow Profile url.**
   I don't have an active StackOverflow profile

2. **Personal website, blog or something you want us to see.**
   1. hadhi-hassan.vercel.app
   2. github.com/hadhihassan
   3. Live project: techunt.vercel.app (freelancing platform with Stripe payments and real-time chat)

   
## The real stuff.
	
1. **Which all programming languages are installed on your system.**
   JavaScript (Node.js), and I have Python installed as well. My primary language for professional work is JavaScript.

2. **Write a function that takes a number and returns a list of its digits in an array.**


```javascript
function digitsOf(num) {
  return Math.abs(num)
    .toString()
    .split('')
    .map(Number);
}
console.log(digitsOf(12345));
console.log(digitsOf(-908));  
```

3. **Remove duplicates of an array and returning an array of only unique elements**

```javascript
function uniqueElementsManual(arr) {
  const seen = {};
  const result = [];
  for (const item of arr) {
    if (!seen[item]) {
      seen[item] = true;
      result.push(item);
    }
  }
  return result;
}
```

4. **Write function that translates a text to Pig Latin and back.**

```javascript
function toPigLatin(text) {
  return text
    .split(' ')
    .map(word => word.slice(1) + word[0] + 'ay')
    .join(' ');
}

function fromPigLatin(text) {
  return text
    .split(' ')
    .map(word => {
      const core = word.slice(0, -2);       
      const firstLetter = core.slice(-1);  
      return firstLetter + core.slice(0, -1);
    })
    .join(' ');
}
const original = "The quick brown fox";
const pig = toPigLatin(original);
console.log(pig);  
console.log(fromPigLatin(pig));
```

5. **Write a function that rotates a list by `k` elements, without creating a copy.**

```javascript
function reverseInPlace(arr, start, end) {
  while (start < end) {
    [arr[start], arr[end]] = [arr[end], arr[start]];
    start++;
    end--;
  }
}

function rotateLeft(arr, k) {
  const n = arr.length;

  if (n === 0) return arr;

  k = k % n;

  if (k === 0) return arr;

  // Reverse first k elements
  reverseInPlace(arr, 0, k - 1);

  // Reverse remaining elements
  reverseInPlace(arr, k, n - 1);

  // Reverse the entire array
  reverseInPlace(arr, 0, n - 1);

  return arr;
}

const arr = [1, 2, 3, 4, 5, 6];

console.log(rotateLeft(arr, 2));
```

**How many swap/move operations does this need?**

The reversal algorithm performs **3 reversals**:

1. **Reverse the first `k` elements**
   - Approximately `k / 2` swaps
2. **Reverse the remaining `n - k` elements**
   - Approximately `(n - k) / 2` swaps
3. **Reverse the entire array**
   - Approximately `n / 2` swaps

Therefore:
```text
Total swaps
≈ k/2 + (n-k)/2 + n/2
= n