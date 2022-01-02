``` cpp

 vector<vector<string> > Anagrams(vector<string>& a) {
map<string,vector<string>>mapp;
string temp;
int i;
        for(i=0;i<a.size();i++)
        {
            temp = a[i];
            sort(temp.begin(), temp.end());
            mapp[temp].push_back(a[i]);
        }
         vector<vector<string>> ans(mapp.size());
         int itr = 0;
         for ( auto x : mapp)
     {
         auto v = x.second;

        for(i =0 ; i<v.size();i++)
        {
         ans[itr].push_back(v[i]);
        }
      itr ++;
     }
    return ans;

    } 
```
