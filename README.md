import java.util.Scanner;

public class StudentExpenseTracker {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Budget: ₱");
        double budget = sc.nextDouble();

        System.out.print("Food Expense: ₱");
        double food = sc.nextDouble();

        System.out.print("Transportation: ₱");
        double transpo = sc.nextDouble();

        System.out.print("School Supplies: ₱");
        double supplies = sc.nextDouble();

        double total = food + transpo + supplies;
        double balance = budget - total;

        System.out.println("\n--- EXPENSE SUMMARY ---");
        System.out.println("Budget: ₱" + budget);
        System.out.println("Total Expenses: ₱" + total);
        System.out.println("Remaining Balance: ₱" + balance);

        sc.close();
    }
}
