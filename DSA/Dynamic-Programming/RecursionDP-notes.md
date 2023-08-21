# Recursion
-function calls itself until a condition is met
-infinite recursion: runs until its out of memory(stack overflow)

## Dynamic Programming

MEMOIZATION: (TOP DOWN)
`import java.util.Arrays;
`public class FibonacciMemoization {
    `static int[] memo;

    static int fibonacci(int n) {
        if (n <= 1) {
            return n;
        }
        
        if (memo[n] != -1) {
            return memo[n];
        }
        
        memo[n] = fibonacci(n - 1) + fibonacci(n - 2);
        return memo[n];
    }

    public static void main(String[] args) {
        int n = 10;
        memo = new int[n + 1];
        Arrays.fill(memo, -1);
        
        System.out.println("Fibonacci(" + n + ") = " + fibonacci(n));
    }
`}

Steps:
1.  make an array of n+1 size filled with -1
2.  add a case for bottom (base case of 1,0)
3.  check if prev solved, return
4.  store curr in memo array and return it


TABULATION: (BOTTOM UP)
`public class FibonacciTabulation {

    static int fibonacci(int n) {
        if (n <= 1) {
            return n;
        }
        
        int[] dp = new int[n + 1];
        dp[0] = 0;
        dp[1] = 1;
        
        for (int i = 2; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }
        
        return dp[n];
    }

    public static void main(String[] args) {
        int n = 10;
        System.out.println("Fibonacci(" + n + ") = " + fibonacci(n));
    }
`}

Steps:
1.  check for bottom case
2.  new dp array
3.  for loop for n times and return it