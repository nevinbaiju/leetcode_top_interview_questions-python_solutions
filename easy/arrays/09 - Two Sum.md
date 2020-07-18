# [Two Sum](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/546/)

The solution to the problem uses hashing, the python implementation uses dictionary which stores the indices in a list for a simple collision resolution mechanism. The worst case computational complexity is O(2n) and the space complexity is O(n).
___
```
def twoSum(nums, target):
    # Creating the hash map.
    hash_map = {}
    for i in range(len(nums)):
        try:
            if(hash_map[nums[i]]):
                hash_map[nums[i]].append(i)
        except KeyError:
            hash_map[nums[i]] = [i]
    # Searching for the indices.
    for i in range(len(nums)):
        remaining_part = target - nums[i]
        try:
            second_element_list = hash_map[remaining_part]
            for element_index in second_element_list:
                if element_index != i:
                    return [i, element_index]
        except KeyError:
            continue
```
___