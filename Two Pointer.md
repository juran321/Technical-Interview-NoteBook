# 反向指针
### 3 sum closest / 3 sum / 3 sum smaller
time: O(n^2)

两个指针， 相向指针，先将数组排序

在固定住一个数 动两个指针， 将总和和target比
### Sort Color
左边的指针都是0，右边的指针都是2，中间都是1

感觉反向要不然是sort好要不然就是让你分类

# 同向指针
### Move Zeroes
两个同向指针， 一个指针指向0, 第二个指针指向非零数，然后swap, 然后第一个指针再找到下一个0, 第二个指针找到下一个非零
数

### Remove Duplicates from Sorted Array i && ii

思路： 双指针， i iterate array. j point to the 1st position after end of the non-dup array, which is length

### Minimum Size Subarray Sum
## 滑动窗口
首先要搞清楚map里面要存的key和value都是什么
```
//初始化map
for(char a :p.toCharArray()) map[a]++;
int left = 0, right = 0, count = p.length();
while(right < s.length){
  1.扩展窗口
  2.通过count，得到一个可能解
  3.只要窗口有可能解，那么缩小窗口知道不包含可能解
}
```
### Longest Substring without repeating characters
### Minimum Window Substring
### Find All Anagrams in a String
