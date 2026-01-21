# -Java-fundamentals-Streams_CodingQuestions-
Emloyee sort,flter,sal grater than less than

Start Date           :time
      21:01:2026     :11:28 Am  

      
Questions

1. This code uses Java 8 Streams to filter employees with salary greater than 4000 using filter() and collects the result into a list using collect(), which is then printed.
package com.ruse;

public class Employee {
    private int id;
    private String name;
    private int sal;

    Employee (int id,String name,int sal){
        this.id=id;
        this.name=name;
        this.sal=sal;
    }

    public int getId(){
        return id;
    }
    public String getName(){
        return name;
    }
    public int getSal(){
        return sal;
    }
}
1 .Q.emloyes Sal >4000
package com.ruse;
import org.springframework.boot.SpringApplication;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
public class AsHardAsYouBreath {
public static void main(String[] args) { 
    List<Employee> employeeList= Arrays.asList(new Employee(1,"bha",25000145),
                new Employee(2,"bhanga",2546847));   //sal grater tan 4000
        List<Employee> collect = employeeList.stream().filter(e -> e.getSal() > 4000).collect(Collectors.toList());
        for (Employee emp:collect){
            System.out.println( "   id      "+ emp.getId());
            System.out.println("    name    "+emp.getName());
            System.out.println("    sal     "+emp.getSal());
        }    }
 
    2. Employee name Start wiith Letter " m" .
    
    public class AsHardAsYouBreath { 
    public static void main(String[] args) {
    List<Employee> employeeList= Arrays.asList(new Employee(1,"bha",25000145),
                new Employee(2,"bhanga",2546847),
                new Employee(3,"mahan",10000000));
                    //Employee nme Strt wwiith " m"
        List<Employee> collect = employeeList.stream().filter(e -> e.getName().startsWith("m") ).collect(Collectors.toList());
        for (Employee emp:collect){
            System.out.println( "   id      "+ emp.getId());
            System.out.println("    name    "+emp.getName());
            System.out.println("    sal     "+emp.getSal());
        } } } }
        
        
      3.  Group the Object(Employee)based on the sal
      
     public class AsHardAsYouBreath {
    public static void main(String[] args) { 
    List<Employee> data= Arrays.asList(new Employee(1,"bha",25000145),
                                        new Employee(2,"bhanga",2546847),
                                        new Employee(3,"mahan",10000000));

        //group the Object(Employee)based on the sal
        Map<Integer,List<Employee>> collect=data.stream().collect(Collectors.groupingBy(e-> e.getSal()));
         System.out.println(collect); 
    // Group employees based on salary
    Map<Integer, List<Employee>> groupedBySal = data.stream()
            .collect(Collectors.groupingBy(Employee::getSal)); 
            
            groupedBySal.forEach((salary, empList) -> {
        System.out.println("Salary: " + salary);
        empList.forEach(emp ->
                System.out.println("   ID: " + emp.getId() + ", Name: " + emp.getName())
        );
        System.out.println();   });
   } }

   4.









