**Search 2D Matrix**
-
🔗 Link: Search 2D Matrix

💡 Difficulty: Medium

🛠️ Topics:Array,Binary Search（二分搜尋）,Matrix

=========================================================

You are given an m x n 2-D integer array matrix and an integer target.

  ．Each row in matrix is sorted in non-decreasing order.
  
  ．The first integer of every row is greater than the last integer of the previous row.
  
Return true if target exists within matrix or false otherwise.

Can you write a solution that runs in O(log(m * n)) time?

Example 1:

Input: matrix = [[1,2,4,8],[10,11,12,13],[14,20,30,40]], target = 10

Output: true

Example 2:

Input: matrix = [[1,2,4,8],[10,11,12,13],[14,20,30,40]], target = 15

Output: false

Constraints:

．m == matrix.length

．n == matrix[i].length

．1 <= m, n <= 100

．-10000 <= matrix[i][j], target <= 10000

=====================================================================

**UMPIRE Method:**

**Understand**

1.每一行的數字是遞增的。

2.每一行的第一個數字大於上一行的最後一個數字，這意味著這個 2D 矩陣可以被視作一個排序的 1D 列表來進行二分搜尋。

3.如果找到 target，回傳 True，找不到就回傳 False。

**Match**

使用二分搜尋法來解這道題目。這個 2D 矩陣其實可以被當作一個 1D 的排序數列來處理，因為每行的結尾與下一行的開頭形成了一個連續遞增的序列。這樣可以利用二分搜尋法來達到 O(log(m * n)) 的時間複雜度。

**Plan**

1.把整個 2D 矩陣視作一個 1D 排序數組，並利用二分搜尋法來搜尋 target。

2.將每個索引位置轉換成矩陣的行和列。

  ．將 2D 矩陣展開視作一個長度為 m * n 的 1D 數組。
  
  ．mid 是在 1D 數組中的索引，對應到 2D 矩陣中的位置是 row = mid // n 和 col = mid % n。

3.通過比較 target 和中間元素來移動搜索範圍。

**Implement**

see solution.py

**Review**

1.邊界條件：我們檢查了矩陣是否為空，如果矩陣或者行是空的，直接回傳 False。

2.時間複雜度：我們在 O(log(m * n)) 時間內搜尋，符合要求。

3.邏輯檢查：通過索引轉換 (mid // n, mid % n)，我們可以有效地將 2D 矩陣展開為一個 1D 列表進行二分搜尋。

**Evaluate**

這個解法能夠處理不同大小的矩陣，無論矩陣是小的還是大的都可以適應。而且，它的空間複雜度是 O(1)，因為我們只使用了固定數量的變量。
