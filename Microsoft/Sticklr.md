```cpp
// { Driver Code Starts
#include <bits/stdc++.h>
using namespace std;
typedef long long int ll;

 // } Driver Code Ends
class Solution
{
    public:
    //Function to find the maximum money the thief can get.
    int FindMaxSum(int a[], int n)
    {
        if(n==1)
            return a[0];
        if(n==2)
            return max(a[0],a[1]);
        
        vector<int> b(n);
        b[0]=a[0], b[1]=a[1], b[2] = a[0]+a[2];
        
        for(int i=3;i<n;i++){
            b[i] = a[i] + max(b[i-2],b[i-3]);
        }
        
        return max(b[n-1],b[n-2]);
    }
};

// { Driver Code Starts.
int main()
{
    //taking total testcases
	int t;
	cin>>t;
	while(t--)
	{
	    //taking number of houses
		int n;
		cin>>n;
		int a[n];
		
		//inserting money of each house in the array
		for(int i=0;i<n;++i)
			cin>>a[i];
		Solution ob;
		//calling function FindMaxSum()
		cout<<ob.FindMaxSum(a,n)<<endl;
	}
	return 0;
}
  // } Driver Code Ends
    ```