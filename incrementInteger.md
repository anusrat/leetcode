Increment an arbitrary precision integer

Time: O(n);
Space: O(n); 

```
class Solution{
vector <int> increment (vector <int> A)
{
    vector <int> res;
    int i, carryout;
    carryout = 1;
    i = A.size()-1;
    
    while(i>=0)
    {
	tmp = A[i] + carryout;
	tmp = tmp%10;
	carryout = tmp/10;
	res.insert(res.begin(),tmp);
	i--;
    }
    
    if(carryout > 0)
    {
        res.insert(res.begin(),carryout);
    }

    return res;
}
```	
