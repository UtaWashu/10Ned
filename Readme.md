**Задача:**
**268.Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array.**
**Решение:**
```cpp
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n = nums.size();
        int ans = n;
        for (int i = 0; i < n; ++i) {
            ans ^= (i ^ nums[i]);
        }
        return ans;
    }
};
```
**Задача:**
**1897.You are given an array of strings words (0-indexed).**
**Решение:**
```cpp
class Solution {
public:
    bool makeEqual(vector<string>& words) {
      vector<int> counter(26, 0);
        for (string word : words) {
            for (char c : word) {
                ++counter[c - 'a'];
            }
        }
        int n = words.size();
        for (int count : counter) {
            if (count % n != 0) return false;
        }
        return true;  
    }
};
```
**Задача:**
**2180.Given a positive integer num, return the number of positive integers less than or equal to num whose digit sums are even.**
**Решение:**
```cpp
class Solution {
public:
    int countEven(int num) {
      int ans = 0;
        for (int i = 1; i <= num; ++i) {
            int s = 0;
            for (int x = i; x; x /= 10) {
                s += x % 10;
            }
            ans += s % 2 == 0;
        }
        return ans;  
    }
};
```