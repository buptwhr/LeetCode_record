# 454 4Sum II
```
class Solution {
public:
    int fourSumCount(vector<int>& A, vector<int>& B, vector<int>& C, vector<int>& D) {
        unordered_map<int,int> CD;
        for(int i=0;i<C.size();i++){
            for(int j=0;j<D.size();j++){
                CD[C[i]+D[j]]++;
            }
        }
        
        int ans = 0;
            
        for(int i=0;i<A.size();i++){
            for(int j=0;j<B.size();j++){
                int temp = A[i] + B[j];
                ans += CD[-temp];
            }
        }
        return ans;
       
    }
};
```

Very similar to Two Sum. Merge A, B and store them in a vector. Merge C, D and store them in a map/unordered map. Try to find $0-number$ in the map.

The difference between map and unordered_map is that the former is organized as a balanced binary tree while the latter is a hash table. So unordered_map has better perfformance.
