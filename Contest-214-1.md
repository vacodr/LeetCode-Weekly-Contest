## 1646. Get Maximum in Generated Array
You are given an integer n. An array nums of length n + 1 is generated in the following way:

nums[0] = 0

nums[1] = 1

nums[2 * i] = nums[i] when 2 <= 2 * i <= n

nums[2 * i + 1] = nums[i] + nums[i + 1] when 2 <= 2 * i + 1 <= n

Return the maximum integer in the array nums​​​.

link: https://leetcode.com/contest/weekly-contest-214/problems/get-maximum-in-generated-array/

Problem type: Easy
# Code
```java
class Solution {
    public int getMaximumGenerated(int n) {
        
        if(n==0)
        {
            return 0;
        }
        
        HashMap<Integer,Integer> m1=new HashMap<Integer,Integer>();
        
        m1.put(0,0);
        m1.put(1,1);
        
        int max = 1,c,b;
        
        for(int i=2;i<=n;i++)
        {
            int a = i/2;
            
            if(i%2!=0)
            {
                 
                 b= i-a;                
            }
            else
            {
                b= 0;
            }
           
            
            c = m1.get(a)+ m1.get(b);
            
            
            if(c>max)
            {
                max=c;
            }
            
            m1.put(i,c);
            
        }
        
        
        return max;
        
    }
}
```
