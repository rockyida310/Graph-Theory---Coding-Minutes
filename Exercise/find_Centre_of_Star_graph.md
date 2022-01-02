```cpp
#include<bits/stdc++.h>
using namespace std;

int findCenter(vector<vector<int>>edges)
{
     //provided that given graph is a star graph
     if(edges.size()==1) return edges[0][0];
     else if(edges[0][0]==edges[1][0] || edges[0][0]==edges[1][1]) return edges[0][1];
     else return edges[0][1];
}
```

Time Complexity : O(1)