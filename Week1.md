
### 238 Product of Array Except Self
对于第i个元素的结果，分成两个部分: 

数字的左边的乘积 * 数字右边的乘积

```
int right =1 ;
for (int i = nums.length - 1; i<=0;i--){
  res[i] *= right;
  right *= nums[i];
}
```
time: O(n)
space: O(n)

### 325 Maximum Size Subarray Sum Equal k

用特殊的数据结构可以把 O(n^2) 降到O(n)

HashMap, Key是prefix sum（累加和）, value 是 index的位置， 值得注意的是 要先存一个(K，V) => (0, -1);


### 56 Merge Interval
这道题首先要想到排序， 然后自己要写一个comparator函数， start小的在前面， 如果start相等的情况下， end小的排在前面。
```
Collections.sort(intervals, new Comparator<Interval>(){
  public int compare(Interval a, Interval b){
    if(a.start!= b.start){
      return a.start-b.start;
    }else{
      return a.end - b.end;
    }
  }
});
```
还有要注意的就是在for loop之后要加上最后一个没有加上的

### 173 Implement an iterator over a BST
用stack进行inorder traversal

```
public int next(){
  while(cur!=null){
    stack.push(cur);
    cur = cur.left;
  }
  
  TreeNode t = stack.pop();
  cur = t.right;
  return t.val;
}

public boolean hasNext(){
  return !stack.isEmpty()||cur!=null;
}
```

### 143 Reorder List
LinkedList

1 2 3 4 5 -> 1 5 2 4 3 

Step1 : find the middle node

Step2 : Revese the right side

Step3 : merge left side and right side

对于第一步， 我们可以运用快慢指针， 当快指针到头时， 慢指针正好在中间的位置， 需要注意的是当指针的长度为偶数的时候慢指针应该停的位置

对于第二步， 可以用iterative或者recursive

iterative
```
ListNode newHead = null;
while(head!=null){
  ListNode next = head.next;
  head.next = newHead;
  newHead = head;
  head = next;
}
return newHead;
```
Recursive

```
public ListNode reverseList(ListNode head) {
    if (head == null || head.next == null) return head;
    ListNode p = reverseList(head.next);
    head.next.next = head;
    head.next = null;
    return p;
}
```

### 208 Implement Trie
