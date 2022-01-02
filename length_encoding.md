```cpp
string encode(string src)
{
    int i;
    int n = src.length();
    for(i=0;i<n;i++){

      int count = 1;
        while (i < n - 1 && src[i] == src[i + 1]) {
     count++;
     i++;
 }
  cout << src[i] << count;
}
}
```
