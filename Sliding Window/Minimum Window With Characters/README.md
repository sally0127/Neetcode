**Minimum Window With Characters**
-
🔗 Link: Minimum Window With Characters

💡 Difficulty: Hard

🛠️ Topics:  字串處理（String Manipulation）,滑動窗口技術（Sliding Window Technique）,字符頻率計算,雙指針技巧（Two Pointer Technique）,邊界情況的處理

==================================================

Given two strings s and t, return the shortest substring of s such that every character in t, including duplicates, is present in the substring. If such a substring does not exist, return an empty string "".

You may assume that the correct output is always unique.

Example 1:

Input: s = "OUZODYXAZV", t = "XYZ"
Output: "YXAZ"

Explanation: "YXAZ" is the shortest substring that includes "X", "Y", and "Z" from string t.

Example 2:

Input: s = "xyz", t = "xyz"
Output: "xyz"

Example 3:

Input: s = "x", t = "xy"
Output: ""

Constraints:

．1 <= s.length <= 1000

．1 <= t.length <= 1000

．s and t consist of uppercase and lowercase English letters.

===========================================================================

**UMPIRE Method:**

**Understand**

1.有兩個字串 s 和 t：

．我們需要找出 s 中的最小子字串，使得該子字串包含 t 中所有的字符（包括重複的字符）。

2.返回結果：

．如果存在這樣的子字串，則返回該子字串。

．如果不存在，則返回空字串 ""。

3.假設：

．假設唯一的正確輸出存在，這樣可以簡化問題。

**Match**

1.計算字符頻率：

．使用 Counter 或字典來計算 t 中每個字符的頻率，了解需要在 s 中找到哪些字符及其數量。

2.初始化滑動窗口：

．使用兩個指針 left 和 right 表示當前窗口的範圍，並使用一個變數來記錄當前窗口中已匹配的字符數量。

3.擴展窗口：

．右指針 right 向右移動，擴展窗口，將當前字符加入窗口並更新頻率計數。

4.縮小窗口：

．當當前窗口包含 t 中所有字符時，使用左指針 left 縮小窗口，更新最小子字串的長度。

5.檢查和更新最小窗口：

．每次找到滿足條件的窗口時，檢查其長度是否小於目前的最小窗口，若是，則更新最小窗口的起始和結束位置。

6.返回結果：

．如果找到的最小窗口有效，返回該子字串；否則返回 ""。

**Plan**

1.初始化計數器：

．使用 Counter 來計算 t 中每個字符的頻率，將其儲存在 dict_t 中。

．初始化一個變數 required，表示 t 中不同字符的總數。

2.設置滑動窗口：

．使用兩個指針 left 和 right，初始化為 0，表示滑動窗口的範圍。

．使用一個變數 formed 來記錄當前窗口中已經匹配的字符數量。

3.使用字典跟蹤窗口字符頻率：

．創建一個 defaultdict(int) 來記錄當前窗口中字符的頻率，命名為 window_counts。

4.擴展右指針：

．進入主循環，當 right 小於 s 的長度時，執行以下步驟：

．取出 s[right]，並將其頻率加入 window_counts。

．如果該字符在 dict_t 中，並且其頻率達到 dict_t 的要求，則將 formed 加 1。

5.檢查是否滿足條件：

．使用一個內部循環，當 formed 等於 required 時，表示當前窗口已包含 t 中的所有字符，執行以下操作：

．檢查窗口的大小，更新最小窗口的長度和起始/結束索引。

．將 s[left] 從窗口中移除，更新 window_counts，並根據需要減少 formed 的計數。

6.移動指針：

．將 right 指針向右移動以擴展窗口，並將 left 指針向右移動以縮小窗口，直到 right 遍歷完整個字串 s。

7.返回結果：

．檢查最小窗口的長度，若未找到合適的子串，返回 ""；否則返回 s[min_left:min_right]，即最小窗口的子字串。

**Implement**

see solution.py

**Review**

1.邊界情況：

．確保對於空字串 s 或 t 的處理，已經正確返回空字串。

2.字典和計數：

．使用 Counter 正確計算了 t 中每個字符的頻率。

．使用 defaultdict 來存儲窗口中的字符頻率，確保在更新時不會出現 KeyError。

3.指針的移動：

．left 和 right 指針的移動邏輯清晰，能夠正確地擴展和縮小窗口。

**Evaluate**

時間和空間複雜度：

．時間複雜度為 O(N)，因為每個指針最多各遍歷一次字串 s。

．空間複雜度主要來自 Counter 和 defaultdict，即 O(M)，其中 M 是字串 t 的長度。

**主要思路**

1.計算頻率：

．首先計算字符串 t 中每個字符的頻率，這樣我們就知道了在字符串 s 中需要滿足的字符和對應的數量。

2.滑動窗口遍歷：

．使用滑動窗口的方式遍歷字符串 s，用兩個指針（left 和 right）來表示當前窗口的邊界。

．每當右指針 right 向右移動時，將新字符的頻率加入到當前窗口的字符頻率字典 window_counts 中。

3.檢查滿足條件：

．當窗口中的字符頻率滿足了 t_count 中的所有需求時，這意味著當前窗口是有效的（即包含了所有需要的字符）。

．此時可以開始嘗試通過移動左指針 left 來縮小窗口，直到不再滿足條件為止。

4.更新最小窗口：

．在每次滿足條件的情況下，檢查當前窗口的大小，並更新最小窗口的邊界。

5.返回結果：

．當遍歷結束後，返回記錄的最小窗口。



