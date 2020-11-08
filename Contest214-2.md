## 5562. Minimum Deletions to Make Character Frequencies Unique
A string s is called good if there are no two different characters in s that have the same frequency.

Given a string s, return the minimum number of characters you need to delete to make s good.

The frequency of a character in a string is the number of times it appears in the string. For example, in the string "aab", the frequency of 'a' is 2, while the frequency of 'b' is 1.

link: https://leetcode.com/contest/weekly-contest-214/problems/minimum-deletions-to-make-character-frequencies-unique/

Problem type: Medium

# Code
```java
class Solution {
    public int minDeletions(String s) {
        
        char f;
        int count=0;
        
        HashMap<Character,Integer> m1=new HashMap<Character,Integer>();
        
        List<Integer> list = new ArrayList<>();
        
        char[] ch = s.toCharArray(); 
        
        for (char c : ch) { 
            if (m1.containsKey(c)) { 
  
                m1.put(c, m1.get(c) + 1); 
            } 
            else { 
  
                m1.put(c, 1); 
            } 
        } 
               
               System.out.println(m1);
        
        for (Integer url : m1.values())  
            list.add(url);
        
        Collections.sort(list);
        
        for(int k:list)
           // System.out.printf(k+"");
        //System.out.println();
        
        
        for(int i= list.size()-1;i>0;i--)
        {
            for(int j= i-1;j>=0;j--)
            {
                if(list.get(i)==0)
                {
                    return count;
                }
                
                int w= list.get(j);
                
                if(list.get(i)==w)
                {
                    list.set(j,w-1);
                    count++;                
                }
                
                
            }
        }
               
               return count;
        
    }
}
```
