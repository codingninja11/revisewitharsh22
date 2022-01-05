``` cpp
unsigned long long getNthUglyNo(int n) {
	   set<unsigned long long> s;
	   s.insert(1);
	   n--;
	   while(n--){
	       auto itr=s.begin();
	       unsigned long long x=*itr;
	       s.erase(itr);

	       s.insert(x*2);
	       s.insert(x*3);
	       s.insert(x*5);
	   }
	   return *s.begin();
}
```