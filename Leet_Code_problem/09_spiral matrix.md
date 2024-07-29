# spiral matrix
Given an m x n matrix, return all elements of the matrix in spiral order.

 

Example 1:

Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]
Output: [1,2,3,6,9,8,7,4,5]

Example 2:

Input: matrix = [[1,2,3,4],[5,6,7,8],[9,10,11,12]]
Output: [1,2,3,4,8,12,11,10,9,5,6,7]

 

Constraints:

    m == matrix.length
    n == matrix[i].length
    1 <= m, n <= 10
    -100 <= matrix[i][j] <= 100

# c++
```
class Solution {
public:
    vector<int> spiralOrder(vector<vector<int>>& matrix) {
        vector<int>result;
        int m=matrix.size();
        int n=matrix[0].size();
        int total=m*n;
        int count=0;

        int startingrow=0;
        int startingcol=0;
        int endingcol=n-1;
        int endingrow=m-1;
        while(count<total){
            // printing first row

            for(int i=startingcol;i<=endingcol && count<total;i++){
                result.push_back(matrix[startingrow][i]);
                count++;
            }
            startingrow++;

            //printing ending col

            for(int i=startingrow;i<=endingrow && count<total;i++){
                result.push_back(matrix[i][endingcol]);
                count++;
            }
            endingcol--;

            //printing last row

            for(int i=endingcol;i>=startingcol && count<total;i--){
                result.push_back(matrix[endingrow][i]);
                count++;
            }
            endingrow--;

            //printing  first col

            for(int i=endingrow;i>=startingrow && count<total;i--){
                result.push_back(matrix[i][startingcol]);
                count++;
            }
            startingcol++;
        }
        return result;
        
    }
};
```
