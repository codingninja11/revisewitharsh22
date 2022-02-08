```cpp
// { Driver Code Starts
//Initial Template for C++
#include <bits/stdc++.h>
#include <unordered_map>
using namespace std;


 // } Driver Code Ends
//User function Template for C++

class Solution{
  public:
   vector<vector<string> > Anagrams(vector<string>& a) {
        map<string,vector<string>>mapp;
        string temp;
        int i;
        
        for(i=0;i<a.size();i++){
            temp = a[i];
            sort(temp.begin(), temp.end());
            mapp[temp].push_back(a[i]);
        }
         vector<vector<string>> ans(mapp.size());
         int itr = 0;
         for ( auto x : mapp){
         auto v = x.second;
         
        for(i =0 ; i<v.size();i++){
         ans[itr].push_back(v[i]);
}
        itr ++;
        }
         return ans;
        
    }
};

// { Driver Code Starts.

int main()
{
    int t;
    cin>>t;
    while(t--)
    {
        int n;
        cin>>n;
        vector<string> string_list(n);
        for (int i = 0; i < n; ++i)
            cin>>string_list[i]; 
        Solution ob;
        vector<vector<string> > result = ob.Anagrams(string_list);
        sort(result.begin(),result.end());
        for (int i = 0; i < result.size(); i++)
        {
            for(int j=0; j < result[i].size(); j++)
            {
                cout<<result[i][j]<<" ";
            }
            cout<<"\n";
        }
    }

    return 0;
}
  // } Driver Code Ends
```
