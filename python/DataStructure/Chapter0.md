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

1、我们在字符串 S 中使用双指针中的左右指针技巧，初始化 left = right = 0，把索引闭区间 [left, right] 称为一个「窗口」。<br>

2、我们先不断地增加 right 指针扩大窗口 [left, right]，直到窗口中的字符串符合要求（包含了 T 中的所有字符）。 <br>

3、此时，我们停止增加 right，转而不断增加 left 指针缩小窗口 [left, right]，直到窗口中的字符串不再符合要求（不包含 T 中的所有字符了）。同时，每次增加 left，我们都要更新一轮结果。<br>

4、重复第 2 和第 3 步，直到 right 到达字符串 S 的尽头。<br>

#### 例1
最小覆盖子串
```c++
string s, t;
// 在 s 中寻找 t 的「最小覆盖子串」
int left = 0, right = 0;
string res = s;

// 相当于两个计数器
unordered_map<char, int> window;
unordered_map<char, int> needs;
for (char c : t) needs[c]++;

// 记录 window 中已经有多少字符符合要求了
int match = 0; 

while (right < s.size()) {
    char c1 = s[right];
    if (needs.count(c1)) {
        window[c1]++; // 加入 window
        if (window[c1] == needs[c1])
            // 字符 c1 的出现次数符合要求了
            match++;
    }
    right++;

    // window 中的字符串已符合 needs 的要求了
    while (match == needs.size()) {
        // 更新结果 res
        res = minLen(res, window);
        char c2 = s[left];
        if (needs.count(c2)) {
            window[c2]--; // 移出 window
            if (window[c2] < needs[c2])
                // 字符 c2 出现次数不再符合要求
                match--;
        }
        left++;
    }
}
return res;
```

#### 例2
找到字符串中所有字母异位词
```py
def find_anagrams(s: str, t: str):
    left = 0
    right = 0
    match = 0
    res = ''

    windows = {}
    needs = {}

    for c in t:
        if c in needs:
            needs[c] += 1
        else:
            needs[c] = 1

    while right < len(s):
        c1 = s[right]
        if c1 in needs:
            if c1 in windows:
                windows[c1] += 1
            else:
                windows[c1] = 1

            if windows[c1] == needs[c1]:
                match += 1
        right += 1
        while match == len(needs):
            if right - left == len(t):
                res += s[left: right] + '\n'
            c2 = s[left]
            if c2 in needs:
                windows[c2] -= 1
                if windows.get(c2, -1) < needs[c2]:
                    match -= 1
            left += 1
    return res
```

