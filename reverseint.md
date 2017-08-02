Reverse digits of an integer.

Example1: x = 123, return 321
Example2: x = -123, return -321
The input is assumed to be a 32-bit signed integer. Your function should return 0 when the reversed integer overflows.

```
class Solution {
public:
    int reverse(int x) {
        string rev_str, str;
        stringstream ss;
        //str = std::to_string(x);
        int i, pos, y, is_negative = 0;
       
        ss << x;
        ss >> str;

        is_negative = x < 0 ? 1 : 0;
        for (i = str.length() - 1; i >= 0; i--)
        {
            if (str[i] == '-')
            {
                break;
            }
            rev_str += str[i];
        }
        
        ss.clear();
        ss << rev_str;
        ss >> y;
        if(is_negative)
        {
         y *= -1;
        }
        return y;
    }
};
```
