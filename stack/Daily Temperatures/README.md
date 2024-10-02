**Daily Temperatures**
-
🔗 Link: Daily Temperatures

💡 Difficulty: Medium

🛠️ Topics: Stack,Array,Monotonic Stack,Traversal

===============================================================

You are given an array of integers temperatures where temperatures[i] represents the daily temperatures on the ith day.

Return an array result where result[i] is the number of days after the ith day before a warmer temperature appears on a future day. If there is no day in the future where a warmer temperature will appear for the ith day, set result[i] to 0 instead.

Example 1:

Input: temperatures = [30,38,30,36,35,40,28]

Output: [1,4,1,2,1,0,0]

Example 2:

Input: temperatures = [22,21,20]

Output: [0,0,0]

Constraints:

．1 <= temperatures.length <= 1000.

．1 <= temperatures[i] <= 100

==============================================================================

**UMPIRE Method:**

**Understand**

1.溫度可以為負嗎？

．是的，溫度可以是負數，這表示低於零的溫度。因此，程式需考慮負值的情況。

2.如果溫度沒有上升，回傳0

．當某一天的溫度之後再也不會有更高的溫度時，該位置的結果應該設置為0。

3.結果陣列的意義

．對於每一天的溫度，返回在這一天之後要等幾天才能出現更高的溫度。如果當天的溫度就是最後一天，則結果為0。

4.陣列的大小

．輸入陣列 temperatures 的大小 n ≥ 1，並且輸出陣列 result 也應該和輸入陣列的大小相同。

5.時間複雜度的考量

．需要考慮如何有效率地計算每一天的結果，以避免超過O(n)的時間複雜度。

**Method**

1.使用堆疊（Stack）

．利用堆疊來追蹤未來的溫度。這樣可以有效地查找更高的溫度出現的天數。

．對於每一天的溫度，我們將其索引放入堆疊中，當找到更高的溫度時，我們就可以計算天數並從堆疊中彈出索引。

**Plan**
1.實作步驟:

．初始化一個 result 陣列，大小與 temperatures 相同，並預設值為 0。

．初始化一個空的堆疊。

．遍歷 temperatures 陣列：

  ．當當前溫度大於堆疊頂部索引的溫度時，表示找到了更高的溫度。
  
  ．計算天數，更新 result 陣列。
  
  ．繼續檢查堆疊中的索引，直到堆疊為空或當前溫度不再大於堆疊頂部的溫度。
  
  ．將當前的索引加入堆疊。

**Implement**

see solution.py

**Review**

1.測試案例

  ．確保測試不同的溫度序列，包括正常情況、所有溫度都上升的情況、所有溫度都下降的情況等。
  
  ．驗證當 temperatures 陣列為單一溫度或包含負數時的行為。

**Evaluate**

1.效能評估

．檢查程式的時間和空間複雜度，應該是 O(n) 的時間複雜度，因為每個溫度只被處理一次。

．確保在大數據集上運行時不會超時或出現記憶體不足的問題。
