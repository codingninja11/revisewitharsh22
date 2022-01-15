```cpp
// { Driver Code Starts
//Initial Template for C++

#include <bits/stdc++.h>
#include <string>

using namespace std;


 // } Driver Code Ends
//User function Template for C++

class Solution
{
    public:
    //Function to find list of all words possible by pressing given numbers.
void print(int i,int arr[],vector<vector<char>>&dict,int n,vector<string>&ans,string str)
    {
        if(i >= n){
            ans.push_back(str);
            return;
        }
        
        int currSize = dict[arr[i]-2].size();
        
        for(int j=0;j<currSize;j++){
            print(i+1,arr,dict,n,ans,str + dict[arr[i]-2][j]);
        }
    }
    
    vector<string> possibleWords(int arr[], int n){
        vector<string> ans;
        vector<vector<char>> dict;
        dict.push_back({'a','b','c'});
        dict.push_back({'d','e','f'});
        dict.push_back({'g','h','i'});
        dict.push_back({'j','k','l'});
        dict.push_back({'m','n','o'});
        dict.push_back({'p','q','r','s'});
        dict.push_back({'t','u','v'});
        dict.push_back({'w','x','y','z'});
        
        print(0,arr,dict,n,ans,"");
        
        return ans;
    }
};


// { Driver Code Starts.

int main() {
  
	int T;
	
	cin >> T; //testcases
	
	while(T--){ //while testcases exist
	   int N;
	    
	   cin >> N; //input size of array
	   
	   int a[N]; //declare the array
	   
	   for(int i =0;i<N;i++){
	       cin >> a[i]; //input the elements of array that are keys to be pressed
	   }
	   
	   Solution obj;
	   
	  vector <string> res = obj.possibleWords(a,N);
	  for (string i : res) cout << i << " ";
	   cout << endl;
	}
	
	return 0;
}  // } Driver Code Ends
```