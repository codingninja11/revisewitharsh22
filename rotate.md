``` cpp
void rotate(int n,int a[][n]){
    int i,j;

    for(i=0;i<n;i++)
            for(j=0;j<i;j++)
            swap(a[i][j] , a[j][i]);
        
        //for reversing elements row-wise
        
        for(i=0;i<n;i++)
            reverse(a,a+n);
        
}  
```