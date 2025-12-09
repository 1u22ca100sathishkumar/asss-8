# asss-8
1. Difference between Compiler Error and Exception
Compiler Error	Exception
Occurs during compilation (before the program runs).	Occurs during runtime (while the program is running).
Caused by violating Java syntax or rules (missing semicolon, wrong type, undefined variable).	Caused by abnormal conditions during execution (divide by zero, accessing invalid array index, null pointer).
Must be fixed before the program can run.	Can be handled using try–catch blocks; program can continue running.
Detected by the compiler.	Detected by the JVM.

3. Java Program: Read an Array Out of Bounds and Handle Exception
public class ArrayOutOfBoundsDemo {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30};

        try {
            // Intentionally accessing out of bounds index
            System.out.println(numbers[5]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Error: Tried to access array outside its range!");
            System.out.println("Exception Message: " + e.getMessage());
        }

        System.out.println("Program continues normally...");
    }
}

4. Java Program: Read Input from User (Scanner) & Handle Divide-by-Zero Exception
import java.util.Scanner;

public class DivideByZeroDemo {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            System.out.print("Enter numerator: ");
            int numerator = scanner.nextInt();

            System.out.print("Enter denominator: ");
            int denominator = scanner.nextInt();

            int result = numerator / denominator;
            System.out.println("Result: " + result);

        } catch (ArithmeticException e) {
            System.out.println("Error: Cannot divide by zero!");
        } catch (Exception e) {
            System.out.println("Invalid input. Please enter numbers only.");
        } finally {
            scanner.close();
        }

        System.out.println("Program finished.");
    }
}
