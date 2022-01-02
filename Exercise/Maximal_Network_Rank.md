
```cpp
#include<bits/stdc++.h>
using namespace std;

int maximalNetworkRank(int n, vector<vector<int>> roads) {
    vector<int> cnt(n,0);
    vector<vector<int>> adjMat(n,vector<int>(n,0));

    for(auto &c:roads){
        adjMat[c[0]][c[1]]=1;
        adjMat[c[1]][c[0]]=1;
        cnt[c[0]]++;
        cnt[c[1]]++;
    }

    int res = 0;

    for(int i=0;i<n;++i){
        for(int j=i+1;j<n;++j){
            res = max(res,cnt[i]+cnt[j]-adjMat[i][j]);
        }
    }

    return res;
}
```