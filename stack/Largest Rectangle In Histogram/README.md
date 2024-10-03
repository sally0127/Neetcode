**Largest Rectangle In Histogram**
-
🔗 Link: Largest Rectangle In Histogram(https://neetcode.io/problems/largest-rectangle-in-histogram)

💡 Difficulty: Hard

🛠️ Topics: 堆疊（Stack）,單調堆疊（Monotonic Stack）,面積計算（Area Calculation）,一維數組遍歷（One-dimensional Array Traversal）,處理邊界情況（Handling Edge Cases）

===========================================================================

You are given an array of integers heights where heights[i] represents the height of a bar. The width of each bar is 1.

Return the area of the largest rectangle that can be formed among the bars.

Note: This chart is known as a histogram.

Example 1:

Input: heights = [7,1,7,2,2,4]
Output: 8

Example 2:

Input: heights = [1,3,7]
Output: 7

Constraints:

．1 <= heights.length <= 1000.

．0 <= heights[i] <= 1000

=============================================================================

**UMPIRE Method:**

**Understand**

1.長度不能為負：確保輸入的 heights 陣列的所有數值均為非負整數。

2.不需要按照高低順序排列：條形的高度可以是任意順序，不必是遞增或遞減的。

3.找出最大矩形的面積：目的是計算在條形圖中可以形成的最大矩形面積。

4.圖形是長條圖：輸入是一個表示長條圖的陣列，每個元素代表一個長條的高度。

**Match**

1.使用堆疊找出最長的圖形：通過使用堆疊來有效地計算每個長條能形成的最大矩形，這是常見的解法。

**Plan**

1.初始化長度：設定一個變數來追踪最大矩形的面積。

2.遍歷每個長條：遍歷 heights 陣列中的每個條形，利用堆疊來跟踪條形的高度及其寬度。

3.計算面積：當當前條形的高度小於堆疊頂部的高度時，從堆疊中彈出高度，計算可以形成的矩形面積，並更新最大面積值。

4.返回結果：遍歷結束後，返回最大面積。

**Implement**

see solution.py

**Review**

驗證邊界情況，例如空的 heights 陣列或所有高度均為0的情況，確保程式能正確處理這些情況。

**Evaluate**

測試不同大小和形狀的 heights 陣列，確保程式的效率和正確性，例如陣列中全是相同高度的條形、隨機高度的條形等。

