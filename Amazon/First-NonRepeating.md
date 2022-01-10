```cpp
// { Driver Code Starts
#include<bits/stdc++.h>
using namespace std;

 // } Driver Code Ends
class Solution {
	public:
		string FirstNonRepeating(string str){
        string res = "";
        deque<char> dq;
        int hash[26]={0};
        
        for(auto i:str){
            int pos = i - 'a';
            if(hash[pos] == 0){
                dq.push_back(i);
            } 
            hash[pos]++;
            
            while(!dq.empty() and hash[dq.front() - 'a'] != 1) dq.pop_front();
            
            if(dq.empty()) res += '#';
            else res += dq.front();   
        }
        return res;
	}

};

// { Driver Code Starts.
int main(){
	int tc;
	cin >> tc;
	while(tc--){
		string A;
		cin >> A;
		Solution obj;
		string res = obj.FirstNonRepeating(A);
		cout << res << "\n";
	}
	return 0;
}  // } Driver Code Ends
```