Given a roman numeral, convert it to an integer.

Input is guaranteed to be within the range from 1 to 3999.

```
class Solution {
public:
    int romanToInt(string s) {
        
        int i,res;
        vector <int> temp;
        i = s.length()-1;
        
        for (i; i >= 0; i--)
        {
            switch (s[i]) 
            {
                case 'I'  : temp.insert(temp.begin(),1);
                                  break;
                case 'V'  : temp.insert(temp.begin(),5);
                                  break;
                case 'X'  : temp.insert(temp.begin(),10);
                                  break;
                case 'L'  : temp.insert(temp.begin(),50);
                                  break;
                case 'C'  : temp.insert(temp.begin(),100);
                                  break;
                case 'D'  : temp.insert(temp.begin(),500);
                                  break;
                case 'M'  : temp.insert(temp.begin(),1000);
                                  break;
            }
        }
        
        i = temp.size()-1;
        res = 0;
        
        for( i; i>=0; i--)
        {
            if(temp[i] < temp[i+1])
            {
                res = res - temp[i];
            }
            else
            {
                res = res + temp[i];
            }
            
        }
        return res;
    }
};
```
