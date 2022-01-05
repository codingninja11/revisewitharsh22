```cpp
#include<bits/stdc++.h>
using namespace std;

 // } Driver Code Ends
class Solution {
	public:
		int CountWays(string str){
            if(str.size()<1) return 0;
            if(str[0]=='0') return 0;
            if(str.size()==1) return 1;
            int l1=1;
            int l2=1;
            for(int i=1;i<str.size();i++){
                int d1=str[i]-'0';
                int d2=(str[i-1]-'0')*10+d1;
                int val=0;
                if(d1>=1) val=(val+l2)%1000000007;
                if(d2>9 && d2<=26) val=(val+l1)%1000000007;
                l1=l2;
                l2=val;
            }
            return l2%1000000007;
}

};

// { Driver Code Starts.
int main(){
	int tc;
	cin >> tc;
	while(tc--){
		string str;
		cin >> str;
		Solution obj;
		int ans = obj.CountWays(str);
		cout << ans << "\n";
	}
	return 0;
}  // } Driver Code Ends
```
