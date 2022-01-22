```cpp
// { Driver Code Starts
//Initial Template for C++

#include <bits/stdc++.h>
using namespace std;

 // } Driver Code Ends
class Solution {
public:
    int helper(vector<int>&A,int i,int j,vector<vector<int>>&dp)
{
   if(i==j)
     return A[i];
   else if(i>j)
     return 0;
   else if(dp[i][j]!=-1)
     return dp[i][j];
   else
   {
       
       int left = A[i] + min(helper(A,i+2,j,dp),helper(A,i+1,j-1,dp));
       
       int right = A[j] + min(helper(A,i+1,j-1,dp),helper(A,i,j-2,dp));
       return dp[i][j] = max(left,right);
   }
}
   int maxCoins(vector<int>&A,int n)
   {
      vector<vector<int>>dp(n,vector<int>(n,-1));
    return  helper(A,0,n-1,dp);
   }
};

// { Driver Code Starts.
int main() {
    int t;
    cin >> t;
    while (t--) {
        int N;
        cin >> N;
        vector<int>A(N);
        for (int i = 0; i < N; i++) {
            cin >> A[i];
        }
        Solution ob;
        cout << ob.maxCoins(A, N) << "\n";
    }
    return 0;
}
  // } Driver Code Ends
  ```