# Payroll
Includes methods of the class called Payroll

package hello;

    public class Payroll 
    {

      private Employee[] employees; //(Imaginary employee class, code wont work without the Employee class)
      private double totalBudget;

      public Payroll(double budget)
      {
        employees = new Employees[0];
        totalBudget = budget;
      }

      public void addEmployee(Employee member)
      {
        Employee[] larger = new Employee[employees.length + 1];
        int i;

        for(int i = 0; i < employees.length; i++)
        {
          larger[i] = employees[i];
        }

        larger[i] = member;
        employees = larger;
      }

      public Employee getEmployee(int id)
      {
        for(Emnployee worker: employees)
        {
          if (worker.getID() == id);
          {
            return worker;
          }
          return null;
        }
      }

      public updatePay(int id, double pay)
      {
        Employee key = this.getEmployee(id);
        if(key != null)
        {
          key.setPayRate(pay);
        }
      }

      public int getOvertimeCount()
      {
        int count = 0;
        for(Employee member: employees)
        {
          if (member.getHoursWorker() > 40)
            count++;
        }
        return count;
      }

      public Employee[] getEmployeesWithOvertime()
      {
        int numberOvertime = this.getOvertimeCount();
        Employee[] overWorker = new Employee[numberOverTime];
        int index = 0;

        for(Employee person: employees)
        {
          if(person.getHoursWorker() > 40)
          {
            overWorked[index] = person;
            index++;
          }
        }
        return overWorked;
      }

      public void payEmployee(int id)
      {
        double[] pay = double[employees.length];

        for(int i = 0; i < employees.length; i++)
        {
          pay[i] = employees[i].getTotalPay();
          employees[i].resetHours();
          totalBudget -= pay;
        }
        printPayChecks(pay);
      }

      public void removeEmployee(int id)
      {
        Employee key = this.getEmployee(id);
        if(key != null)
        {
          Employee[] staff = new Employee[employees.length -1];
          int index = 0;

          for(Employee employ: employees)
          {
            if(employ != key)
            {
              staff[index] = employ;
              index++;

            }
            employees = staff;
          }
        }
      }

      public void printPayChecks(double[] payChecksAmount)
      {
        /* implementation hidden*/

      }

      public void setBudget(double budget)
      {
        totalBudget = budget;
      }

      public double getBudget()
      {
        return totalBudget;
      }
    }

