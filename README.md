
import java.util.Scanner;

public class StudentExpenseTracker {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        double budget, total = 0;
        String history = "";
        int choice;

        System.out.println("=== STUDENT EXPENSE TRACKER ===");
        System.out.print("Enter Budget: PHP ");
        budget = sc.nextDouble();

        do {
            System.out.println("\n===== MAIN MENU =====");
            System.out.println("1. Add Expense");
            System.out.println("2. View Summary");
            System.out.println("3. Expense History");
            System.out.println("4. Exit");
            System.out.print("Choose: ");
            choice = sc.nextInt();

            switch (choice) {
                case 1:
                    System.out.println("\n1. Food");
                    System.out.println("2. Transportation");
                    System.out.println("3. School Supplies");
                    System.out.println("4. Others");
                    System.out.print("Category: ");
                    int category = sc.nextInt();

                    String name;
                    switch (category) {
                        case 1: name = "Food"; break;
                        case 2: name = "Transportation"; break;
                        case 3: name = "School Supplies"; break;
                        case 4: name = "Others"; break;
                        default:
                            System.out.println("Invalid category!");
                            continue;
                    }

                    System.out.print("Amount: PHP ");
                    double amount = sc.nextDouble();

                    if (amount <= 0) {
                        System.out.println("Invalid amount!");
                        break;
                    }

                    total += amount;
                    history += name + ": PHP " + amount + "\n";

                    System.out.println("Expense Added!");

                    if (total > budget)
                        System.out.println("WARNING: Budget Exceeded!");
                    break;

                case 2:
                    System.out.println("\n--- EXPENSE SUMMARY ---");
                    System.out.printf("Budget: PHP %.2f%n", budget);
                    System.out.printf("Expenses: PHP %.2f%n", total);
                    System.out.printf("Balance: PHP %.2f%n", budget - total);
                    break;

                case 3:
                    System.out.println("\n--- EXPENSE HISTORY ---");
                    System.out.println(history.isEmpty()
                            ? "No expenses yet." : history);
                    break;

                case 4:
                    System.out.println("Thank you for using the system!");
                    break;

                default:
                    System.out.println("Invalid choice!");
            }

        } while (choice != 4);

        sc.close();
    }
}
