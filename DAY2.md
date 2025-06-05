# Day 2 Learning Progress

## What I Learned Today
- 2D Arrays and matrix operations
- Advanced loop constructs and flow control
- HCF/LCM applications in real-world problems

## Code I Wrote
import java.util.Scanner;

class practical_examples {

    public static void main(String[] args) {
        // Example calls for testing
        printNumberPyramid(5);

        System.out.println("Is 17 prime? " + isPrime(17));

        calculator(); // Run calculator
    }

    // Number Pyramid Program
    public static void printNumberPyramid(int rows) {
        for (int i = 1; i <= rows; i++) {
            // Print spaces for alignment
            for (int space = 1; space <= rows - i; space++) {
                System.out.print(" ");
            }

            // Print numbers
            for (int num = 1; num <= i; num++) {
                System.out.print(num + " ");
            }

            System.out.println(); // Move to next line
        }
    }

    // Prime Number Checker
    public static boolean isPrime(int number) {
        if (number <= 1) return false;
        if (number <= 3) return true;
        if (number % 2 == 0 || number % 3 == 0) return false;

        // Check for divisors from 5 onwards
        for (int i = 5; i * i <= number; i += 6) {
            if (number % i == 0 || number % (i + 2) == 0) {
                return false;
            }
        }
        return true;
    }

    // Calculator Using Switch-Case
    public static void calculator() {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter first number: ");
        double num1 = scanner.nextDouble();

        System.out.print("Enter operator (+, -, *, /): ");
        char operator = scanner.next().charAt(0);

        System.out.print("Enter second number: ");
        double num2 = scanner.nextDouble();

        double result = 0;
        boolean validOperation = true;

        switch (operator) {
            case '+':
                result = num1 + num2;
                break;
            case '-':
                result = num1 - num2;
                break;
            case '*':
                result = num1 * num2;
                break;
            case '/':
                if (num2 != 0) {
                    result = num1 / num2;
                } else {
                    System.out.println("Error: Division by zero!");
                    validOperation = false;
                }
                break;
            default:
                System.out.println("Error: Invalid operator!");
                validOperation = false;
        }

        if (validOperation) {
            System.out.println("Result: " + result);
        }

        scanner.close();
    }
}


## Challenges Faced
- Understanding spiral matrix traversal logic
- Debugging off-by-one errors in array bounds

## Tomorrow's Goals
- Practice more complex matrix algorithms
- Start working on a small project combining these concepts
