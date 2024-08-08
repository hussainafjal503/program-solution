# Java _Static _Initializer_Block_solution.java

```
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        Scanner in=new Scanner(System.in);
        int b=in.nextInt();
        int h=in.nextInt();
        if(h>0 && b>0)
            System.out.println(b*h);
        else
            System.out.println( "java.lang.Exception: Breadth and height must be positive");
    }
}
```
