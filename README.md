# LEETCODE-Array-1701
Let's go through the dry run of the given `averageWaitingTime` method step-by-step with an example. 

Consider the following input:

```java
int[][] customers = {{1, 2}, {2, 5}, {4, 3}};
```

Here, each element in the `customers` array represents a customer. The first element of each sub-array is the arrival time of the customer, and the second element is the time required to prepare their order.

### Step-by-Step Dry Run:

1. **Initialization**:
   ```java
   double wait = 0;
   double curr = 0;
   ```
   - `wait` is initialized to 0. This variable will accumulate the total waiting time.
   - `curr` is initialized to 0. This variable represents the current time.

2. **First customer `[1, 2]`**:
   ```java
   curr = Math.max(curr, 1.0 * c[0]) + c[1];
   wait += curr - c[0];
   ```
   - `curr = Math.max(0, 1.0 * 1) + 2 = 3`
   - `wait += 3 - 1 = 2`
   - Now, `wait = 2` and `curr = 3`.

3. **Second customer `[2, 5]`**:
   ```java
   curr = Math.max(curr, 1.0 * c[0]) + c[1];
   wait += curr - c[0];
   ```
   - `curr = Math.max(3, 1.0 * 2) + 5 = 8`
   - `wait += 8 - 2 = 6`
   - Now, `wait = 8` and `curr = 8`.

4. **Third customer `[4, 3]`**:
   ```java
   curr = Math.max(curr, 1.0 * c[0]) + c[1];
   wait += curr - c[0];
   ```
   - `curr = Math.max(8, 1.0 * 4) + 3 = 11`
   - `wait += 11 - 4 = 7`
   - Now, `wait = 15` and `curr = 11`.

5. **Final Calculation**:
   ```java
   return 1.0 * wait / customers.length;
   ```
   - `return 1.0 * 15 / 3 = 5.0`

The average waiting time for the given example is `5.0`.

### Summary of the Process:

- For each customer, calculate the current time by taking the maximum of the current time and the customer's arrival time, then add the time required to prepare the order.
- Update the total waiting time by adding the difference between the current time and the customer's arrival time.
- Finally, calculate the average waiting time by dividing the total waiting time by the number of customers.

The method efficiently computes the average waiting time for all customers based on their arrival times and order preparation times.
