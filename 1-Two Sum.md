# 1 Two Sum
```C++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int,int> my;
        vector<int> ans;
        for (int i=0;i<nums.size();i++)
            my[nums[i]] = i+1;
        
        for(int i=0;i<nums.size();i++){
            if(my[target-nums[i]]!=0 && my[target-nums[i]] != (i+1)){
                ans.push_back(i);
                ans.push_back(my[target-nums[i]] - 1);
                break;
            }
        }
        return ans;       
    }
};
```
Use map/unordered_map to store the <number,its index+1>. If key-value pairs' v is 0, the key doesn't appear in the vector. The unordered_map is kind of a hash table. Then traverse the vector and look for $ target-number $ in the map.
