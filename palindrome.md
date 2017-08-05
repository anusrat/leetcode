Determine whether an integer is a palindrome. Do this without extra space.
Some hints:
Could negative integers be palindromes? (ie, -1)

If you are thinking of converting the integer to string, note the restriction of using extra space.

You could also try reversing an integer. However, if you have solved the problem "Reverse Integer", you know that the reversed integer might overflow. How would you handle such case?

There is a more generic way of solving this problem.

O(n) solution
Time: 182 ms

```
class Solution {
public:
    bool isPalindrome(int x) {
        int i,j, count = 1;
        string s;
        bool result = true;
        s = to_string(x);
        int flag;
        if (x%2 == 0){flag = 1;} else{flag = 0;}
        i = 0;
        j = s.length()-1;
        
        while(i < s.length() && j >=0 && i!=j)
        {
            if (flag && (count <= s.length()/2))
            {
                if(s[i] != s[j])
                {
                    result = false;
                    break;
                }
                count++; i++; j--;
            }
            else
            {
                if(s[i] != s[j])
                {
                    result = false;
                    break;
                }
                i++; j--;
             }
        }
        return result;
    }
};
```
