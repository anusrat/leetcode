CTCI: 1.1 (pg. 192)
Implement an algorithm to determine if a string has all unique chracters. You cannot use additional datastructures.

Time: O(n log n)
```
bool isUnique(string str)
{
	bool res = true;;
	int i,j;
	char cache;
    
	/* 1. Sort the string
	   2. Iterate the string and cache the characters at pos i
	   3. If char exists in cache, return false
	*/
    str.sort(str.begin(), str.end());  ---> O(n log n)
    for (i = 0; i < str.length(); i++  ---> O(n)
	{
		if(str[i] != cache)
		{
			cache = str[i];
		}
		else
		{
			res = false;
			break;
		}
	}
	return res;
}
```
