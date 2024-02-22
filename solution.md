# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->

# Approach
<!-- Describe your approach to solving the problem. -->

# Complexity
- Time complexity:
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```
class Solution {
public:
    int findJudge(int n, vector<vector<int>>& trust) {
        vector<int> trustCounts(n + 1, 0);
        vector<bool> trusteds(n+1, false);

        for(const auto& t: trust)
        {   
            trusteds[t[0]] = true;
            trustCounts[t[1]]++;
        }
        for(int i = 1; i <= n; i++)
        {
            if(!trusteds[i] && trustCounts[i] == n-1)
                return i;
        }
        return -1;
    }
};
```