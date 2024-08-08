# 539. Minimum Time Difference

Given a list of 24-hour clock time points in "HH:MM" format, return the minimum minutes difference between any two time-points in the list.

 
Example 1:

Input: timePoints = ["23:59","00:00"]
Output: 1

Example 2:

Input: timePoints = ["00:00","23:59","00:00"]
Output: 0

 
Constraints:

    2 <= timePoints.length <= 2 * 104
    timePoints[i] is in the format "HH:MM".

# Java
```
class Solution {
    public int findMinDifference(List<String> timePoints) {
        List<Integer> result=new ArrayList<Integer>();
        for(String str:timePoints){
            int hour=Integer.parseInt(str.substring(0,2));
            int min=Integer.parseInt(str.substring(3));
            int total=min+(60*hour);
            result.add(total);
        }

        Collections.sort(result);

        int minimum=Integer.MAX_VALUE;
        for(int i=0;i<result.size()-1;i++){
            int diff=result.get(i+1)-result.get(i);
            minimum=Math.min(minimum,diff);
        }
       
        int ldiff1=(result.get(0)+1440)-(result.get(result.size()-1));
          minimum=Math.min(minimum,ldiff1);
        int ldiff2=(result.get(result.size()-1))-(result.get(0));
          minimum=Math.min(minimum,ldiff2);

        return minimum;
    }

}
```
