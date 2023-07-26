<$ocover/>

```js
/**
Name: two-sum
Order: 1

* Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
给定一个整数数组 nums 和一个整数目标值 target，请你在该数组中找出 和为目标值 target  的那 两个 整数，并返回它们的数组下标。

You may assume that each input would have exactly one solution, and you may not use the same element twice.
你可以假设每种输入只会对应一个答案。但是，数组中同一个元素在答案里不能重复出现。

You can return the answer in any order.
你可以按任意顺序返回答案。

算法的时间复杂度为O(n)，其中n为数组中元素的个数。使用哈希表来存储元素和下标的对应关系; 
**/

// soulation 1
var twoSum = function(nums, target) {
  const map = new Map(); // 创建一个空的哈希表
  for (let i = 0; i < nums.length; i++) {
    const diff = target - nums[i]; // 计算目标值与当前元素的差值
    if (map.has(diff)) { // 在哈希表中查找是否存在值等于差值的元素
      return [map.get(diff),i]; // 如果存在，则返回这两个元素的下标
    }
    map.set(nums[i], i); // 如果不存在，则将当前元素和下标存入哈希表中
  }
};

// soulation 2
function twoSum(nums, target) {
  for (let i = 0; i < nums.length; i++) {
    for (let j = i + 1; j < nums.length; j++) {
      if (nums[i] + nums[j] === target) {
        return [i, j];
      }
    }
  }
  return [];
}
```