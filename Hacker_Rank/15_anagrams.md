# Two strings, and

, are called anagrams if they contain all the same characters in the same frequencies. For this challenge, the test is not case-sensitive. For example, the anagrams of CAT are CAT, ACT, tac, TCA, aTC, and CtA.

Function Description

Complete the isAnagram function in the editor.

isAnagram has the following parameters:

    string a: the first string
    string b: the second string

Returns

    boolean: If 

and

    are case-insensitive anagrams, return true. Otherwise, return false.

Input Format

The first line contains a string
.
The second line contains a string

.

Constraints

Strings and

    consist of English alphabetic characters.
    The comparison should NOT be case sensitive.

Sample Input 0

anagram
margana

Sample Output 0

Anagrams

Explanation 0
Character 	Frequency: anagram 	Frequency: margana
A or a 	3 	3
G or g 	1 	1
N or n 	1 	1
M or m 	1 	1
R or r 	1 	1

The two strings contain all the same letters in the same frequencies, so we print "Anagrams".

Sample Input 1

anagramm
marganaa

Sample Output 1

Not Anagrams

Explanation 1
Character 	Frequency: anagramm 	Frequency: marganaa
A or a 	3 	4
G or g 	1 	1
N or n 	1 	1
M or m 	2 	1
R or r 	1 	1

The two strings don't contain the same number of a's and m's, so we print "Not Anagrams".

Sample Input 2

Hello
hello

Sample Output 2

Anagrams

Explanation 2
Character 	Frequency: Hello 	Frequency: hello
E or e 	1 	1
H or h 	1 	1
L or l 	2 	2
O or o 	1 	1

The two strings contain all the same letters in the same frequencies, so we print "Anagrams".

# Java
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        
        Scanner in=new Scanner(System.in);
        String str=in.next();
        String lower=str.toLowerCase();
        
        String out=in.next();
        out=out.toLowerCase();
        int arr[]=new int[256];
        for(int i=0;i<lower.length();i++){
            
            arr[lower.codePointAt(i)]++;
        }
        
        for(int j=0;j<out.length();j++){
            arr[out.codePointAt(j)]--;
        }
        
        boolean flag=true;
        for(int i=0;i<arr.length;i++){
            if(arr[i]!=0){
                System.out.println("Not Anagrams");
                flag=false;
                break;    
                }
        
        }
        if(flag==true)
            System.out.println("Anagrams");
    }
}
```
