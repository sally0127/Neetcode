**Median of Two Sorted Arrays**
-
🔗 Link: Median of Two Sorted Arrays

💡 Difficulty: Hard

🛠️ Topics: Binary Search（二分搜尋）,Divide and Conquer（分治法）,Median（中位數）,Edge Case Handling（邊界情況處理）

================================================================

You are given two integer arrays nums1 and nums2 of size m and n respectively, where each is sorted in ascending order. Return the median value among all elements of the two arrays.

Your solution must run in O(log(m+n)) time.

Example 1:

Input: nums1 = [1,2], nums2 = [3]
Output: 2.0

Explanation: Among [1, 2, 3] the median is 2.

Example 2:

Input: nums1 = [1,3], nums2 = [2,4]
Output: 2.5

Explanation: Among [1, 2, 3, 4] the median is (2 + 3) / 2 = 2.5.

Constraints:

．nums1.length == m

．nums2.length == n

．0 <= m <= 1000

．0 <= n <= 1000

．-10^6 <= nums1[i], nums2[i] <= 10^6

=======================================================================================

**UMPIRE Method**

**Understand**

1.輸入：兩個已排序的整數數組 nums1 和 nums2。

2.輸出：返回兩個數組組合後的中位數。

3.特性：兩個數組均為升序排列。

4.挑戰：要求 O(log(m+n)) 時間複雜度。

**Match**

1.合併兩個數組並排序 是最直接的方法，但時間複雜度為 O(m+n)，不符合題意。

2.二分法 可以幫助我們快速找到中位數，而不需要合併數組，這樣可以達到 O(log(m+n)) 時間複雜度。

**Plan**

我們將問題轉換成在兩個數組中找到一個切分點，使得左半部分和右半部分的元素數量相等或接近相等。根據中位數的定義：

．當總長度為奇數時，中位數是左半部分的最大值。

．當總長度為偶數時，中位數是左半部分的最大值與右半部分的最小值的平均值。

具體步驟如下：

1.將較短的數組稱為 A，較長的數組稱為 B（這樣可以減少計算量）。

2.對 A 進行二分搜尋，嘗試在 A 中找到一個切分點，使得左半部分的最大值小於右半部分的最小值。

3.定義切分點 i 和 j，使得 i + j 等於兩個數組左半部分的總數量。

4.比較 A[i-1]、B[j-1]、A[i] 和 B[j] 的大小來判斷中位數。

**Implement**

see solution.py

**Review**

1.邊界情況：檢查其中一個數組為空的情況。

2.測試：測試數組長度相差很大的情況，或者兩數組都為奇數或偶數長度的情況。

**Evaluate**

這個解法的時間複雜度為 O(log(min(m,n)))，符合題意的要求，並且有效地處理了邊界情況。



