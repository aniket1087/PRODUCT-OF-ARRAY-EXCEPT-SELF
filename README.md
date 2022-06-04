# PRODUCT-OF-ARRAY-EXCEPT-SELF
![image](https://user-images.githubusercontent.com/102652030/172004984-52c00986-4f88-49b5-a856-b9382598427a.png)
//LEETCODE PROBLEM;
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        int n=nums.size();
        vector<int> res(n);
        res[0]=1;
        int pre=1;
        for(int i=1;i<n;i++){
            pre=pre*nums[i-1];
            res[i]=pre;
        }
        int post=1;
        for(int i=n-1;i>=0;i--){
            res[i]=res[i]*post;
            post=post*nums[i];
        }
        return res;
    }
};
