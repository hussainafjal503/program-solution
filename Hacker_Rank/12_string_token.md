# string_token
Given a string, , matching the regular expression [A-Za-z !,?._'@]+, split the string into tokens. We define a token to be one or more consecutive English alphabetic letters. Then, print the number of tokens, followed by each token on a new line. Note: You may find the String.split method helpful in completing this challenge.

Input Format: - A single string, . Constraints is composed of any of the following: English alphabetic letters, blank spaces, exclamation points (!), commas (,), question marks (?), periods (.), underscores (_), apostrophes ('), and at symbols (@). Output Format

On the first line, print an integer, , denoting the number of tokens in string (they do not need to be unique). Next, print each of the tokens on a new line in the same order as they appear in input string

.

Sample Input

He is a very very good boy, isn't he?

Sample Output

10 He is a very very good boy isn t he
```
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        String s = scan.nextLine();
        // Write your code here.
        
        s=s.trim(); //for removing space from begining
        if(s.length()==0)
        {
            System.out.println(0);
            return;
        }
        String[] words=s.split("[^a-zA-Z]+");//for spliting the string if any other character come instead of alphabet.
        System.out.println(words.length);//printing the length of the string 
        for(String word:words)
        {
            System.out.println(word);
        }
        scan.close();
    }
}
```
