Question :- https://leetcode.com/problems/spiral-matrix/

```
class Solution {
    public List<Integer> spiralOrder(int[][] matrix) {
        List<Integer> res = new ArrayList<>();
        
        if(matrix.length == 0 || matrix == null)
            return res;
        
        int t = 0, b = matrix.length - 1;
        int l = 0, r = matrix[0].length - 1;       
        
        while(t<=b && l<=r){
            
            for(int i=l;i<=r;i++)
                res.add(matrix[t][i]);
            
            t++;
            
            for(int i=t;i<=b;i++)
                res.add(matrix[i][r]);
            
            r--;
            
            if(t<=b){
                for(int i=r;i>=l;i--)
                    res.add(matrix[b][i]);
                b--;
            }
            
            
            if(l<=r){
                for(int i=b;i>=t;i--)
                    res.add(matrix[i][l]);
                l++;
            }
               
        }
        return res;
    }
}
```
