# “Explain to me, as if I was a beginning JavaScript student, what a recursion is.”

## Response

Sure! Let's break down the concept of recursion in JavaScript step by step.

### What is Recursion?

Recursion is a programming technique where a function calls itself to solve smaller instances of the same problem until it reaches a base case (a condition that stops the recursion).

### Understanding Recursion with an Example

Think of recursion like looking into two mirrors facing each other. You see an endless reflection of yourself. Similarly, in recursion, a function keeps calling itself until a condition is met to stop the calls.

### A Simple Example: Factorial

Let's look at a simple example: calculating the factorial of a number. The factorial of a number `n` (written as `n!`) is the product of all positive integers from 1 to `n`.

#### Factorial Example Breakdown

- `5! = 5 * 4 * 3 * 2 * 1`
- `3! = 3 * 2 * 1`

Notice that:

- `5! = 5 * 4!`
- `4! = 4 * 3!`
- And so on...

### Recursive Function for Factorial

Here's how you can write a recursive function to calculate the factorial of a number in JavaScript:

```javascript
function factorial(n) {
  // Base case: if n is 0, return 1 (0! is defined as 1)
  if (n === 0) {
    return 1;
  }
  // Recursive case: n * factorial of (n - 1)
  return n * factorial(n - 1);
}

// Testing the function
console.log(factorial(5)); // Output: 120
```

### How It Works

1. **Base Case**: The function checks if `n` is 0. If it is, the function returns 1. This is the stopping condition that prevents infinite recursion.

   ```javascript
   if (n === 0) {
     return 1;
   }
   ```

2. **Recursive Case**: If `n` is not 0, the function returns `n` multiplied by the result of calling `factorial` with `n - 1`. This breaks the problem into smaller instances.

   ```javascript
   return n * factorial(n - 1);
   ```

### Step-by-Step Execution

Let's see what happens when you call `factorial(5)`:

1. `factorial(5)`:
   - Not 0, so it returns `5 * factorial(4)`
2. `factorial(4)`:
   - Not 0, so it returns `4 * factorial(3)`
3. `factorial(3)`:
   - Not 0, so it returns `3 * factorial(2)`
4. `factorial(2)`:
   - Not 0, so it returns `2 * factorial(1)`
5. `factorial(1)`:
   - Not 0, so it returns `1 * factorial(0)`
6. `factorial(0)`:
   - This is the base case, so it returns `1`

Now, all the calls start returning their results:

- `factorial(1)` returns `1 * 1` = `1`
- `factorial(2)` returns `2 * 1` = `2`
- `factorial(3)` returns `3 * 2` = `6`
- `factorial(4)` returns `4 * 6` = `24`
- `factorial(5)` returns `5 * 24` = `120`

### Key Points to Remember

- **Base Case**: This is crucial to stop the recursion. Without a base case, the function would call itself indefinitely and cause a stack overflow error.
- **Recursive Case**: This is where the function calls itself with a smaller or simpler argument, gradually working towards the base case.
- **Stack**: Each function call is placed on the call stack until the base case is reached, then the stack unwinds as each call returns its result.

Recursion can be a bit tricky to understand at first, but with practice, you'll see that it's a powerful tool for solving problems that can be broken down into smaller, similar problems.
