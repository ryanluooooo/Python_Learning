### two pointer（双指针）

指的是在遍历元素的过程中，使用两个指针来进行访问。常见的有对撞指针、快慢指针、分离双指针



* ==对撞指针==：两个指针方向相反。适合解决查找有序数组中满足某些约束条件的一组元素问题、字符串反转问题。

* ==快慢指针==：两个指针方向相同。适合解决数组中的移动、删除元素问题，或者链表中的判断是否有环、长度问题。

* ==分离双指针==：两个指针分别属于不同的数组 / 链表。适合解决有序数组合并，求交集、并集问题。



e g. 对撞指针应用

==**Day4**==

**leetcode_problem344_"Reverse String"**  （反转字符串）

example:

```py
Input: s = ["h","e","l","l","o"]
Output: ["o","l","l","e","h"]
```

code:

```py
class Solution:
    def reverseString(self, s: List[str]) -> None:
        """
        Do not return anything, modify s in-place instead.
        """
        left = 0
        right = len(s) - 1
        while left < right:
            s[left], s[right] = s[right], s[left]
            left += 1
            right -= 1
        return s
```





e g. 快慢指针应用

==**Day2**==

**leetcode_problem26_"Remove Duplicates from Sorted Array"**  （删除有序数组中的重复项）

example:

```py
Input: nums = [1,1,2]
Output: 2, nums = [1,2,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 1 and 2 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).
```

code:

```py
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        # 定义两个指针
        slow = 0
        fast = 1
        # 可以视作把非重复元素放在数组左边
        while fast < len(nums):
            if nums[slow] != nums[fast]:
                slow += 1
                nums[slow] = nums[fast]
            fast += 1
        return slow + 1
```

