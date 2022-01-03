```cpp
class Solution{
  public:
    int countSubArrayProductLessThanK(const vector<int>& a, int n, long long k) {
         long long int start=0,end=0,count=0,product=1;
       while(end<n){
           product *= a[end];
           while(start<n and product>=k){
               product = product/a[start];
               start++;
           }
           if(product<k)
           count+=end-start+1;

           end++;
       }
       return count;
    }
};
```


<!-- Input : 
n = 4, k = 10
a[] = {1, 2, 3, 4}
Output : 
7
Explanation:
The contiguous subarrays are {1}, {2}, {3}, {4} 
{1, 2}, {1, 2, 3} and {2, 3} whose count is 7. -->

<!-- Approach: Two pointers start & end
initialize 4 variables start,end,count,productuct -->