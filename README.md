1.	Encapsulation is the bundling of data and methods that operate on the data into a single unit, called a class. It hides the internal state of an object from the outside world and only exposes the necessary functionality through well-defined interfaces. 
Create an Employee class having data members' Name, Eid, and Basic_Salary, to calculate the HRA is 20% of Basic Salary and DA is 25% of Basic salary and MA is 300 rupee. implement the following queries:
  a) Display the name and gross salary of an employee whose name starts With 'n'
  b).Display the Eid and gross salary whose Eid is equal to 107.
  c)  Count the total number of employees whose salary more than 20000/-
import java.util.ArrayList;

class salary {
    private String name;
    private int eid;
    private double basicSalary;

    public Employee(String name, int eid, double basicSalary) {
        this.name = name;
        this.eid = eid;
        this.basicSalary = basicSalary;
    }

    public String getName() {
        return name;
    }

    public int getEid() {
        return eid;
    }

    public double getBasicSalary() {
        return basicSalary;
    }

    public double calculateGrossSalary() {
        double hra = 0.2 * basicSalary;
        double da = 0.25 * basicSalary;
        double ma = 300;
        return basicSalary + hra + da + ma;
    }
}

public class Main {
    public static void main(String[] args) {
        ArrayList<Employee> employees = new ArrayList<>();
        employees.add(new Employee("John", 101, 25000));
        employees.add(new Employee("Mary", 102, 30000));
        employees.add(new Employee("Nancy", 103, 18000));
        employees.add(new Employee("Nick", 104, 22000));
        System.out.println("Employees whose name starts with 'N':");
        for (Employee emp : employees) {
            if (emp.getName().toUpperCase().startsWith("N")) {
                System.out.println("Name: " + emp.getName() + ", Gross Salary: " + emp.calculateGrossSalary());
            }
        }
        int targetEid = 107;
        System.out.println("\nEmployee with Eid " + targetEid + ":");
        for (Employee emp : employees) {
            if (emp.getEid() == targetEid) {
                System.out.println("Eid: " + emp.getEid() + ", Gross Salary: " + emp.calculateGrossSalary());
                break; // assuming Eid is unique, so no need to continue after finding the employee
            }
        }
        int count = 0;
        for (Employee emp : employees) {
            if (emp.getBasicSalary() > 20000) {
                count++;
            }
        }
        System.out.println("\nTotal number of employees with salary more than 20000: " + count);
    }
}
