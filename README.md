using System;
using System.Collections.Generic;

class FinanceTracker
{
    static void Main()
    {
        List<double> incomes = new();
        List<double> expenses = new();

        while (true)
        {
            Console.WriteLine("\n1. Add Income\n2. Add Expense\n3. Summary\n4. Exit");
            Console.Write("Choose: ");
            int choice = int.Parse(Console.ReadLine());

            switch(choice)
            {
                case 1:
                    Console.Write("Enter income amount: ");
                    incomes.Add(double.Parse(Console.ReadLine()));
                    break;

                case 2:
                    Console.Write("Enter expense amount: ");
                    expenses.Add(double.Parse(Console.ReadLine()));
                    break;

                case 3:
                    double totalIncome = 0, totalExpense = 0;
                    incomes.ForEach(i => totalIncome += i);
                    expenses.ForEach(e => totalExpense += e);

                    Console.WriteLine($"Total Income: {totalIncome}");
                    Console.WriteLine($"Total Expense: {totalExpense}");
                    Console.WriteLine($"Balance: {totalIncome - totalExpense}");
                    break;

                case 4:
                    return;
            }
        }
    }
}
