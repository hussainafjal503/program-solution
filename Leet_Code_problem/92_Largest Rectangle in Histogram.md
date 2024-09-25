# 84. Largest Rectangle in Histogram

Given an array of integers heights representing the histogram's bar height where the width of each bar is 1, return the area of the largest rectangle in the histogram.


Example 1:

Input: heights = [2,1,5,6,2,3]
Output: 10
Explanation: The above is a histogram where width of each bar is 1.
The largest rectangle is shown in the red area, which has an area = 10 units.

Example 2:

Input: heights = [2,4]
Output: 4


Constraints:

    1 <= heights.length <= 105
    0 <= heights[i] <= 104

# Java
```java
class Solution {
    public int [] smallestPre(int []num){
        Stack<Integer> st=new Stack<>();
        st.push(-1);

        int ans[]=new int[num.length];
        for(int i=0;i<num.length;i++){
            int curr=num[i];
            while(st.peek()!=-1 && num[st.peek()]>=curr){
                st.pop();
            }
            ans[i]=st.peek();
            st.push(i);
        }
        return ans;
    }


    public int [] smallestNext(int []num){
        Stack<Integer> st=new Stack<>();
        st.push(-1);

        int ans[]=new int[num.length];
        for(int i=num.length-1;i>=0;i--){
            int curr=num[i];
            while(st.peek()!=-1 && num[st.peek()]>=curr){
                st.pop();
            }
            ans[i]=st.peek();
            st.push(i);
        }
        return ans;
    }
    public int largestRectangleArea(int[] heights) {
        int []prev=smallestPre(heights);
        int []next=smallestNext(heights);
        int size=heights.length;
        int maxArea=Integer.MIN_VALUE;

        for(int i=0;i<heights.length;i++){
            int len=heights[i];
            if(next[i]==-1){
                next[i]=size;
            }
                int width=next[i]-prev[i]-1;
                int area=len*width;
                maxArea=Math.max(maxArea,area);
        }
        return maxArea;
    }
}
```
