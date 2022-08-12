# Leetcode Practice problems

# 1. 2 Sums

class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        dic = {}
        for i, n in enumerate(nums): 
            diff = target - n 
            if diff in dic:
                return [dic[diff], i]
            dic[n] = i
        return

# 2. Roman to Integer

class Solution:
    def romanToInt(self, s: str) -> int:
        # Largest to smallest: add them up
        # Smallest before largest: subtract smaller
        # Refer neetcode

        roman_dict = {
            'I' :1,
            'V' :5,
            'X' :10,
            'L' :50,
            'C' :100,
            'D' :500,
            'M' :1000
        }
        
        res = 0
        for i in range(len(s)):
            if i + 1 < len(s) and roman_dict[s[i]] < roman_dict[s[i + 1]]:
                res -= roman_dict[s[i]] 
            else:
                res += roman_dict[s[i]]
        return res
