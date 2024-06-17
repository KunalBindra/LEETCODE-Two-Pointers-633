# LEETCODE-Two-Pointers-633
**APPROACH - 1**
Let's perform a dry run of the `judgeSquareSum` method in the `Solution` class with a specific example, say `c = 5`.

Here's the `Solution` class and the `judgeSquareSum` method:

```java
class Solution {
    public boolean judgeSquareSum(int c) {
        long a = 0;
        long b = (long) Math.sqrt(c);

        while (a <= b) {
            long k = a * a + b * b;

            if (k < c) {
                a++;
            } else if (k > c) {
                b--;
            } else {
                return true;
            }
        }

        return false;
    }
}
```

**Example: \( c = 5 \)**

1. **Initial Setup**: 
   - `c = 5`
   - `a = 0`
   - `b = (long) Math.sqrt(5) = 2`

2. **First Iteration**:
   - Calculate \( k \):
     \[
     k = a * a + b * b = 0 * 0 + 2 * 2 = 0 + 4 = 4
     \]
   - Check if \( k < c \):
     \[
     4 < 5 \quad (\text{True})
     \]
   - Increment `a`:
     \[
     a = 1
     \]

3. **Second Iteration**:
   - Calculate \( k \):
     \[
     k = a * a + b * b = 1 * 1 + 2 * 2 = 1 + 4 = 5
     \]
   - Check if \( k == c \):
     \[
     5 == 5 \quad (\text{True})
     \]
   - Since the condition is true, the method returns `true`.

**Conclusion**:
- The method returns `true` for \( c = 5 \), indicating that 5 can be expressed as the sum of two squares \( 1^2 + 2^2 \).

**General Behavior**:
- The loop runs while \( a \leq b \).
- For each iteration, it calculates \( k = a * a + b * b \).
- If \( k < c \), it increments `a`.
- If \( k > c \), it decrements `b`.
- If \( k == c \), it returns `true`.
- If no such pair is found by the end of the loop, it returns `false`.

This method effectively checks if a given integer `c` can be expressed as the sum of two squares.
**APPROACH - 2**
Let's perform a dry run of the `judgeSquareSum` method in the `Solution` class with a specific example, say `c = 5`.

Here's the `Solution` class and the `judgeSquareSum` method:

```java
class Solution {
    public boolean judgeSquareSum(int c) {
        for (long a = 0; a * a <= c; a++) {
            double b = Math.sqrt(c - a * a);
            if (b == (int) b) {
                return true;
            }
        }
        return false;
    }
}
```

**Example: \( c = 5 \)**

1. **Initial Setup**: 
   - `c = 5`
   - Start the loop with `a = 0`

2. **First Iteration (a = 0)**:
   - Calculate \( a * a \):
     \[
     0 * 0 = 0
     \]
   - Check if \( 0 \leq 5 \) (True)
   - Calculate \( b \):
     \[
     b = \sqrt{5 - 0} = \sqrt{5} \approx 2.236
     \]
   - Check if \( b == (int)b \):
     \[
     2.236 \neq 2 \quad (\text{False})
     \]

3. **Second Iteration (a = 1)**:
   - Increment `a` to 1
   - Calculate \( a * a \):
     \[
     1 * 1 = 1
     \]
   - Check if \( 1 \leq 5 \) (True)
   - Calculate \( b \):
     \[
     b = \sqrt{5 - 1} = \sqrt{4} = 2.0
     \]
   - Check if \( b == (int)b \):
     \[
     2.0 == 2 \quad (\text{True})
     \]
   - Since the condition is true, the method returns `true`.

4. **Conclusion**:
   - The method returns `true` for \( c = 5 \), indicating that 5 can be expressed as the sum of two squares \( 1^2 + 2^2 \).

**General Behavior**:
- The loop runs from `a = 0` to \( a \) such that \( a * a \leq c \).
- For each `a`, it calculates `b` as the square root of \( c - a * a \).
- It checks if `b` is an integer by comparing `b` to `(int)b`.
- If such a pair `(a, b)` is found, it returns `true`.
- If no such pair is found by the end of the loop, it returns `false`.

This method effectively checks if a given integer `c` can be expressed as the sum of two squares.

