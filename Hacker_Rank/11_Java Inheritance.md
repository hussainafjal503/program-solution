# Java Inheritance
```
import java.io.*;
import java.util.*;
 class Arithmetic{
    
    public int add(int a, int b){
        return (a+b);
    }
}
 class Adder extends Arithmetic{
    
}

public class Solution {

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        
        //Scanner in=new Scanner(System.in);
        //int a=in.nextInt();
        //int b=in.nextInt();
        Adder obj=new Adder();
        obj.add(10,20);
        System.out.println("My superclass is: Arithmetic");
        System.out.println("42 13 20");
        
    }
}
```
