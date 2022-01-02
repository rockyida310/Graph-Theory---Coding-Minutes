
```cpp
#include<bits/stdc++.h>
using namespace std;

int minTrioDegree(int n, vector<vector<int>> edges) {
    vector<vector<int>> adjMat(n,vector<int>(n,0));
    vector<int> conn(n,0);
    
    for(auto &c:edges){
        adjMat[c[0]-1][c[1]-1]=1;
        adjMat[c[1]-1][c[0]-1]=1;
        conn[c[1]-1]++;
        conn[c[0]-1]++;
    }
    
    int res = INT_MAX;
    
    for(int i=0;i<n;++i){
        for(int j=i+1;j<n;++j){
            for(int k=j+1;k<n;++k){
                
                if(adjMat[i][j] && adjMat[j][k] && adjMat[k][i]){
                    res = min(res,conn[i]+conn[j]+conn[k]-6);
                }
                
            }
        }
    }
    
    return res==INT_MAX ? -1 : res;    
}
```