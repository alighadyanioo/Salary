# Salary
//the salary of the difrent type of employee
package com.company;

import java.util.Scanner;

abstract class Employee {
    protected String id;
    protected int salary;

    abstract public int getSalary();


    public Employee(String id) {
        this.id = id;
    }

    public String getId() {
        return id;
    }

    public void setId(String id) {
        this.id = id;
    }

    public String toString() {
        return id;
    }
}

class HourlyEmployee extends Employee {
    protected String id;
    protected int timeWork;

    public HourlyEmployee(String id) {
        super(id);
    }

    @Override
    public int getSalary() {
        return timeWork*50000;
    }

    public void setTimeWork(int timeWork) {
        this.timeWork = timeWork;
    }

    public String toString() {
        return id;
    }
}

class ProjectEmployee extends Employee {
    protected String employeeId;
    protected int levelOfProject;

    public ProjectEmployee(String employeeId) {
        super(employeeId);
    }

    @Override
    public int getSalary() {
        return levelOfProject();
    }

    private int levelOfProject() {
        return levelOfProject;
    }

    public int getLevelOfProject() {
        return levelOfProject;
    }

    public void setLevelOfProject(int levelOfProject) {
        this.levelOfProject = levelOfProject;
    }
}

class NormalEmployee extends Employee {
    protected String employeeId;

    public NormalEmployee(String employeeId) {
        super(employeeId);
    }

    @Override
    public int getSalary() {
        return salary;
    }

    public void setSalary(int salary) {
        this.salary = salary;
    }

    public String toString() {
        return employeeId;
    }
}

public class main1 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        do {
            System.out.println();
            System.out.println("Which employee you want to check?:");
            System.out.println("1)Hourly: " + "2)Project: " + "3)Final(Monthly):");
            int number = scanner.nextInt();
            if (number == 1) {

                //the Hourly Employee
                String salary = "Salary: ";
                HourlyEmployee hourly = new HourlyEmployee("255478");
                System.out.println("Please enter the time of work:");
                int time = scanner.nextInt();
                hourly.setTimeWork(time);
                System.out.println("The Employee:" + hourly.getId() + " " + "With This Time: " + time +"Hours"+ "  " + salary + hourly.getSalary());
                System.out.println();
            } else if (number == 2) {
                //the Project employee
                ProjectEmployee projectEmployee = new ProjectEmployee("255786");
                System.out.println("1) Level (A) :2000$" + "\n2) Level (B) :1000$" + "\n3) Level (C) :500$");
                System.out.println("Please enter the Level of Project:");
                int levelProject = scanner.nextInt();

                switch (levelProject) {
                    case 1 -> System.out.println(" The Level is: " + levelProject + " " + "salary:" + "2000$");
                    case 2 -> System.out.println(" The Level is: " + levelProject + " " + "salary:" + "1000$");
                    case 3 -> System.out.println(" The Level is: " + levelProject + " " + "salary:" + "500$");
                    default -> System.out.println("Please inter valid Character...!!!");
                }
            } else if (number == 3) {
                NormalEmployee simpleEmployee = new NormalEmployee("255748");
                System.out.println("enter the Salary:");
                int salary = scanner.nextInt();
                simpleEmployee.setSalary(salary);
                System.out.println("The Salary is:" + simpleEmployee.getSalary());

            }
        } while (true);
    }
}
