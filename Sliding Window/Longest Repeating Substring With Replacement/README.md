**Longest Repeating Substring With Replacement**
-
🔗 Link: Longest Repeating Substring With Replacemen

💡 Difficulty: Medium

🛠️ Topics: 

=======================================================

You are given a string s consisting of only uppercase english characters and an integer k. You can choose up to k characters of the string and replace them with any other uppercase English character.

After performing at most k replacements, return the length of the longest substring which contains only one distinct character.

Example 1:

Input: s = "XYYX", k = 2
Output: 4

Explanation: Either replace the 'X's with 'Y's, or replace the 'Y's with 'X's.

Example 2:

Input: s = "AAABABB", k = 1
Output: 5

Constraints:

．1 <= s.length <= 1000

．0 <= k <= s.length

=========================================================================

**UMPIRE Method:**

**Understand**

．我們有一個由大寫字母組成的字串 s 和一個整數 k。

．我們可以最多替換 s 中的 k 個字符，使得一個子串的所有字符都變成相同的字符。

．目標是返回這樣的最長子串的長度。

**Match**

．因為我們要尋找能使子串中的字符都相同的最長子串，所以可以考慮滑動窗口來逐步檢查每一個窗口內的字符是否能通過最多 k 次替換，達到子串中的所有字符都相同的條件。

．使用一個頻率字典來記錄窗口中每個字符的出現次數，這樣能方便計算出窗口內字符的最大頻率（即一個字符出現的最多次數）。

**Plan**

．使用滑動窗口，窗口的左、右邊界分別用 left 和 right 指針表示。

．當窗口中最多的字符出現次數為 max_count 時，可以用 right - left + 1 - max_count 來判斷窗口中剩下的字符數量是否大於 k。

．若大於 k，則表示無法在這個窗口內達到要求，應該縮小窗口，將 left 向右移動；否則，繼續增大窗口。

．每次符合條件時，更新最大子串長度 max_length。

**Implement**

see solution.py

**Review**

．確保每次 left 和 right 的移動邏輯正確。

．確認 max_count 的更新方式，確保每次窗口內的最大頻率是正確的。

．滑動窗口和頻率字典的使用符合時間複雜度 O(n)，其中 n 是字串長度。

**Evaluate**

．時間複雜度：因為每個字符最多訪問一次（右指針）並且 left 只移動一次，因此整體時間複雜度是 O(n)。

．空間複雜度：由於 char_count 字典最多只存儲 26 個字母的頻率，因此空間複雜度是 O(1)。

===================================================================================

**總體邏輯：**

1.擴大窗口：使用右指針 right 不斷向右移動，擴大窗口來包含新的字符。

2.檢查條件：在每次擴大窗口後，計算當前窗口的大小 (right - left + 1)，然後檢查當前窗口內需要替換的字符數量，即 (right - left + 1) - max_count 是否大於 k。

3.縮小窗口：如果需要替換的字符數量超過了 k，那麼就需要進入 while 循環，縮小窗口。這是通過移動左指針 left 來實現的：

  ．在 while 循環中，減少字符計數 char_count[s[left]]，然後將 left 向右移動一位，這樣就縮小了窗口。

4.重複過程：當窗口符合條件後，繼續擴大右指針 right，重複上述步驟，直到遍歷完整個字符串。

