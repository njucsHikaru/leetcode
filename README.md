# leetcode
## 1. Two Sum <Easy>
Given an array of integers, return indices of the two numbers such that they add up to a specific target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
Example:
  
Given nums = [2, 7, 11, 15], target = 9,
Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].

**Stupid Solution**: n^2:iterator*2 --> easy

define the array: 
`
int[] array = new int[n];
`

**Recommended Solution**: using a map, then minus the current value, judge if the target - value in the map. If yes, then return these two indices.
```
public int[] twoSum(int[] numbers, int target) {
    int[] result = new int[2];
    Map<Integer, Integer> map = new HashMap<Integer, Integer>();
    for (int i = 0; i < numbers.length; i++) {
        if (map.containsKey(target - numbers[i])) {
            result[1] = i + 1;
            result[0] = map.get(target - numbers[i]);
            return result;
        }
        map.put(numbers[i], i + 1);
    }
    return result;
}
```

## 2. Add Two Numbers <Medium>
  You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

Example:

Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8
Explanation: 342 + 465 = 807.

**Data Structure**: ListNode
```
Definition for singly-linked list.
public class ListNode
{
    int val;
    ListNode next;

    public ListNode(int x){
        val=x;
    }
  
}
```


