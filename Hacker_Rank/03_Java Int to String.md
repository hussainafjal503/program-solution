# Java Int to String_solution
```

import java.util.*;
import java.security.*;
public class Solution {
 public static void main(String[] args) 
 {
    Scanner in = new Scanner(System.in);
     int n = in .nextInt();
     
     //String s=???; Complete this line below

     
     String s=Integer.toString(n);
   
     if (n == Integer.parseInt(s))
     {
          System.out.println("Good job");
   } 
   else
   {
    System.out.println("Wrong answer.");
   }
```
