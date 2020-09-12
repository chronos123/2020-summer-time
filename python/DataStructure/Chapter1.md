# 学习网址
https://github.com/labuladong/fucking-algorithm


## 动态规划

最优子结构：要符合「最优子结构」，子问题间必须互相独立 <br>
状态转换方程 <br>
重叠子问题 <br>
<br>
可以用递归备忘录 <br>
也可以用数组实现 <br>
状态是原问题和子问题中变化的量

## 回溯算法详解

前序遍历选择，后序遍历撤销

## 二分查找

框架
```c++
int binarySearch(int[] nums, int target) {
    int left = 0, right = ...;

    while(...) {
        int mid = left + (right - left) / 2;
        if (nums[mid] == target) {
            ...
        } else if (nums[mid] < target) {
            left = ...
        } else if (nums[mid] > target) {
            right = ...
        }
    }
    return ...;
}
```

左侧边界寻找， left = right（符合条件的）
```c++
int left_bound(int[] nums, int target) {
    if (nums.length == 0) return -1;
    int left = 0;
    int right = nums.length; // 注意
    
    while (left < right) { // 注意
        int mid = (left + right) / 2;
        if (nums[mid] == target) {
            right = mid;
        } else if (nums[mid] < target) {
            left = mid + 1;
        } else if (nums[mid] > target) {
            right = mid; // 注意
        }
    }
    return left;
}
```

右侧边界寻找
```c++
int right_bound(int[] nums, int target) {
    if (nums.length == 0) return -1;
    int left = 0, right = nums.length;
    
    while (left < right) {
        int mid = (left + right) / 2;
        if (nums[mid] == target) {
            left = mid + 1; // 注意
        } else if (nums[mid] < target) {
            left = mid + 1;
        } else if (nums[mid] > target) {
            right = mid;
        }
    }
    return left - 1; // 注意
}
```

## 滑动窗口

