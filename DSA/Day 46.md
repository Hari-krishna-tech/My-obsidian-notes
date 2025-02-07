# Next Greater Element
Tag : [[MonotonicStack]]

# Intuition


<!-- Describe your first thoughts on how to solve this problem. -->

Monotonic stacks, in order to find the next greater element

  

# Complexity

- Time complexity:


$$O(n)$$

  

- Space complexity:


$$O(n)$$

  

# Code

```java []

class Solution {

public int[] nextGreaterElement(int[] nums1, int[] nums2) {

HashMap<Integer, Integer> map = new HashMap<>();

  

// monotonic stack

Stack<Integer> stack = new Stack<>();

int n = nums1.length;

int m = nums2.length;

  

for(int i = m - 1; i >= 0; i--) {

// top of the stack should be greater or empty (next greater element)

while(!stack.isEmpty() && stack.peek() < nums2[i]) {

stack.pop();

}

// if empty add -1, or current top

if(!stack.isEmpty()) {

map.put(nums2[i], stack.peek());

} else {

map.put(nums2[i], -1);

}

// add the current number

// monotonic decreasing stack

stack.push(nums2[i]);

}

  

// it is trivial now

int[] ans = new int[n];

for(int i = 0; i < n; i++) {

ans[i] = map.get(nums1[i]);

}

return ans;

}

}

```