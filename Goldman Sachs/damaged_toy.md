```cpp
#include <bits/stdc++.h>
using namespace std;

 // } Driver Code Ends


class Solution {
  public:
    int findPosition(int n , int m , int k) {
        if (m <= n - k + 1)
       return m + k - 1;

   m = m - (n - k + 1);

   return (m % n == 0) ? n : (m % n);
    }
};

// { Driver Code Starts.
int main() {
    int t;
    cin >> t;
    while (t--) {
        int N,M,K;
        
        cin>>N>>M>>K;

        Solution ob;
        cout << ob.findPosition(N,M,K) << endl;
    }
    return 0;
}  // } Driver Code Ends
```
We check if the number of items to be distributed is greater than our remaining positions in current cycle of circle or not. If yes, then we simply return m + k – 1 (We distribute items in same cycle starting from k). Else we compute number of remaining items after completing current cycle and return mod of remaining items.
