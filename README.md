# -Java-fundamentals-Streams_CodingQuestions-
Emloyee sort,flter,sal grater than less than

Start Date           :time
      21:01:2026     :11:28 Am  

Questions


  1. This code uses Java 8 Streams to filter employees with salary greater than 4000 using filter() and collects the result into a list using collect(), which is then printed.
   package com.ruse; 
  2. Employee name Start wiith Letter " m" .
  3.  Group the Object(Employee)based on the sal
  4. Second max salary sal
  5.second low salary
  6.  To get employees details  by their salary salary
  7.To get employees   salary >50000
   
  
    
    

      
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

   4. Second max salary sal
 
 public class AsHardAsYouBreath {
    public static void main(String[] args) {
        List<Employee> emps= Arrays.asList(new Employee(1,"bha",1),
                new Employee(2,"bhanga",2),
                new Employee(3,"mahan", 3),
                new Employee(3,"foura", 4),
                new Employee(3,"bherra", 5));
        //Second m salary sal
        OptionalInt first = emps.stream().mapToInt(e -> e.getSal()).distinct().sorted().skip(emps.size() - 2).findFirst() ;
        System.out.println(first.isPresent() );
        System.out.println("Second high salary sal "+first.getAsInt()); 
      }  } 


 5.second low salary 
 
public class AsHardAsYouBreath {
    public static void main(String[] args) { 
    List<Employee> emps= Arrays.asList(new Employee(1,"bha",1),
                new Employee(2,"bhanga",2),
                new Employee(3,"mahan", 3),
                new Employee(4,"foura", 4),
                new Employee(5,"bherra", 5)); 
                //second low salary
        int n=emps.stream().mapToInt(e->e.getSal()).distinct().sorted().skip(1).findFirst().getAsInt();
        System.out.println(n); 
        }
 } 
 
 6.  To get employees details  by their salary salary
   
public class AsHardAsYouBreath {
    public static void main(String[] args) {

        List<Employee> emps= Arrays.asList(new Employee(1,"bha",500000000),
                new Employee(2,"bhanga",30000000),
                new Employee(3,"mahan", 200000000),
                new Employee(4,"foura", 100000000),
                new Employee(5,"bherra", 100000000));

        //To get employees details  by their salary salary
        List<Employee> emp= emps.stream().filter(e->e.getSal()==100000000).collect(Collectors.toList());
        for (Employee g:emp) {
            System.out.println(g.getId()+"_____ "+g.getName()+ "______"+ g.getSal() );
        }  }); } }


  7.To get employees   salary >50000
  public class AsHardAsYouBreath {
    public static void main(String[] args) {
      List<Employee> emps= Arrays.asList(new Employee(1,"bha",500000000),
                new Employee(2,"bhanga",30000000),
                new Employee(3,"mahan", 200000000),
                new Employee(4,"foura", 100000000),
                new Employee(5,"bherra", 100000000));
       //To get employees   salary >50000
        List<Employee> emp = emps.stream().filter(e->e.getSal()>50000).collect(Collectors.toList());
        for (Employee em:emp ) {
            System.out.println(em.getId()+"   "+em.getName()+ "   "+ em.getSal() );
        }  } }














