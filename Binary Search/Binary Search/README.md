**Binary Search**
-
🔗 Link:Binary Search

💡 Difficulty: Easy

🛠️ Topics: Binary Search (二分搜尋法) ,Array (數組),Divide and Conquer (分治法)

============================================================================

You are given an array of distinct integers nums, sorted in ascending order(升序), and an integer target.

Implement a function to search for target within nums. If it exists, then return its index, otherwise, return -1.

Your solution must run in O(logn) time.

Example 1:

Input: nums = [-1,0,2,4,6,8], target = 4
Output: 3

Example 2:

Input: nums = [-1,0,2,4,6,8], target = 3
Output: -1

Constraints:

．1 <= nums.length <= 10000.
．-10000 < nums[i], target < 10000

=====================================================================================

**UMPIRE Method**:

**Understand**

1.在已經排序好的數列 nums 裡找一個 target，如果找到就回傳它的索引 (index)，如果找不到，回傳 -1。

2.nums 數列中的元素是唯一的 (distinct)，不會有重複的數字。

3.數列 nums 是按照升序排列的。

4.題目沒有特別限制數列是否包含負數，所以假設可以有。

5.你的解法需要在 O(logn) 的時間內完成。這提示你應該用二分搜尋法（Binary Search）。

**Match**

1.二分搜尋法是一種在排序數列中查找元素的高效算法，時間複雜度是 O(logn)，非常適合這題的要求。

2.核心思想是每次將搜尋範圍縮小一半，從中間元素開始比較，然後根據比較結果選擇繼續在左半部分或右半部分搜索。

**Plan**

1.初始化兩個指標 left 和 right，分別指向數列的開頭和結尾。

2.每次計算中間位置 mid，然後比較 nums[mid] 和 target：
  
  ．如果 nums[mid] == target，返回 mid。
  
  ．如果 nums[mid] < target，將 left 移到 mid + 1，縮小範圍至右半部分。
  
  ．如果 nums[mid] > target，將 right 移到 mid - 1，縮小範圍至左半部分。

3.當 left 超過 right 時，說明找不到 target，返回 -1。

**Implement**

see solution.py

**Review**

1.測試範例：

．nums = [1, 2, 3, 4, 5, 6, 7, 8, 9], target = 5 -> output = 4 (因為索引為 4)

．nums = [-5, -3, 0, 2, 4, 6], target = -3 -> output = 1

．nums = [1, 3, 5, 7], target = 8 -> output = -1

2.你可以嘗試一些邊界情況，如空數組 ([])、單一元素的數組等。

**Evaluate**

1.這個解法已經符合 O(logn) 的時間複雜度要求，效率很高。

2.檢查是否還有可能的優化點，並確認各種測試案例的正確性。你也可以進行大規模測試，以確保算法的性能。
