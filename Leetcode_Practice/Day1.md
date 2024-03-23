Day1

```py
# Day1 "Two Sum"
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        n = len(nums)
        for i in range(0,n-1):
            for j in range(i+1,n):
                if nums[i] + nums[j] == target:
                    return [i,j]
        return []

''' 
line3 "self" 用于表示类的实例（对象）自身
line3 对函数的参数和返回值进行"类型注解",nums是整数列表,target是整数,返回值是整数列表       
      "->" 用来表示函数的返回值类型
'''
```



xianzaigaibian
