**Sliding Window Maximum**
-
🔗 Link: Sliding Window Maximum

💡 Difficulty: Hard

🛠️ Topics: 滑動窗口技術 (Sliding Window Technique), 雙端隊列 (Deque)

========================================================

You are given an array of integers nums and an integer k. There is a sliding window of size k that starts at the left edge of the array. The window slides one position to the right until it reaches the right edge of the array.

Return a list that contains the maximum element in the window at each step.

Example 1:

Input: nums = [1,2,1,0,4,2,6], k = 3

Output: [2,2,4,4,6]

Explanation: 
Window position            Max
---------------           -----
[1  2  1] 0  4  2  6        2
 1 [2  1  0] 4  2  6        2
 1  2 [1  0  4] 2  6        4
 1  2  1 [0  4  2] 6        4
 1  2  1  0 [4  2  6]       6

Constraints:

．1 <= nums.length <= 1000

．-1000 <= nums[i] <= 1000

．1 <= k <= nums.length

===================================================================

**UMPIRE Method:**

**Understand**

題目要求在給定的整數數組 nums 和整數 k 的情況下，找出每個大小為 k 的滑動窗口的最大值。隨著窗口在數組中向右滑動，返回一個包含每個窗口最大值的列表。

**Match**

選擇使用 雙端隊列 (deque)，它允許在兩端進行快速添加和刪除操作。這使得在遍歷數組時能夠高效地管理窗口中的元素，特別是在移除不再需要的元素和保持當前窗口的最大值。

**Plan**

1.初始化一個雙端隊列 deq 用來存儲元素的索引，並初始化一個列表 max_values 用來儲存每個窗口的最大值。

2.遍歷 nums 數組，對於每個索引 i：                                                        
                                                                                                                                                                                                                                                                       
．移除 deq 中不在當前窗口的索引。                                                                                                                                                

．移除所有小於當前元素的索引，確保 deq 只保留可能成為最大值的索引。                          

．將當前索引 i 添加到 deq。                                                               也就是說，先移除不在窗口的元素，才能移動到下一個，之後在對比新的窗口哪一個比較小，再把它刪除留下最大值，之後再把將當前索引 i(最大值) 添加到 deq 中，

．當窗口大小達到 k 時，將 deq 的首個元素對應的值（即當前窗口的最大值）添加到 max_values。      當 i 大於或等於 k - 1 時，表示已經形成了一個完整的窗口，此時可以將 deq[0] 對應的值（即當前窗口的最大值）添加到 max_values 中，這樣，每次窗口移動時，都能保持對最大值的高效追踪。整個過程使得該演算法的時間複雜度為 O(N)，因為每個元素最多只會進入和退出 deq 一次。

**Implement**

see solution.py

**Review**

確保邊界情況已處理，例如空數組或 k 為 0 的情況。

測試不同大小的數組和 k 值，以確保功能的正確性。

**Evaluate**

．時間複雜度為 O(N)，因為每個元素最多進出雙端隊列一次。

．空間複雜度為 O(k)，因為在最壞情況下，隊列可能儲存 k 個索引。

