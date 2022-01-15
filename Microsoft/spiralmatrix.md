```cpp
// { Driver Code Starts
#include <bits/stdc++.h> 
using namespace std; 

 // } Driver Code Ends
class Solution
{   
    public: 
    //Function to return a list of integers denoting spiral traversal of matrix.
    vector<int> spirallyTraverse(vector<vector<int> > matrix, int r, int c) 
    {
        vector<int>ans;
        int rs =0,re =r-1; //row starting and row end
        int cs =0,ce =c-1; //col starting and col end
        int i=0;
        while(rs<=re && cs<=ce){
            if(i%2==0){
                for(int j=cs;j<=ce;j++){
                    ans.push_back(matrix[rs][j]);
                }
                rs++;
                for(int j=rs;j<=re;j++){
                    ans.push_back(matrix[j][ce]);
                }
                ce--;
                
            }
            else{
                for(int j=ce;j>=cs;j--) ans.push_back(matrix[re][j]);
                re--;
                for(int j=re;j>=rs;j--) ans.push_back(matrix[j][cs]);
                cs++;
            }
            i++;
        }
        return ans;
    }
};

// { Driver Code Starts.
int main() {
    int t;
    cin>>t;
    
    while(t--) 
    {
        int r,c;
        cin>>r>>c;
        vector<vector<int> > matrix(r); 

        for(int i=0; i<r; i++)
        {
            matrix[i].assign(c, 0);
            for( int j=0; j<c; j++)
            {
                cin>>matrix[i][j];
            }
        }

        Solution ob;
        vector<int> result = ob.spirallyTraverse(matrix, r, c);
        for (int i = 0; i < result.size(); ++i)
                cout<<result[i]<<" ";
        cout<<endl;
    }
    return 0;
}  // } Driver Code Ends
```