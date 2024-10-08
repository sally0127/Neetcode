**Longest Substring Without Duplicates**
-
🔗 Link:Longest Substring Without Duplicates

💡 Difficulty: Medium

🛠️ Topics:滑動窗口（Sliding Window）,哈希集（Hash Set）,雙指針技術（Two-pointer Technique）

========================================================================

Given a string s, find the length of the longest substring without duplicate characters.

A substring is a contiguous sequence of characters within a string.

Example 1:

Input: s = "zxyzxyz"
Output: 3

Example 2:

Input: s = "xxxx"
Output: 1

Constraints:

．0 <= s.length <= 1000

．s may consist of printable ASCII characters.

=========================================================================================

**UMPIRE Method:**


**Understand**

1.給定一組字串 s，需要找出最長的子字串（substring）。

2.子字串是連續的字符序列。

3.在找到的子字串中，不允許有重複的字符。

**Match**

1.這題確實可以使用Sliding Window技術來解決。

2.使用兩個指針（left 和 right）來維持當前的窗口，這個窗口將擴展或收縮以確保它包含不重複的字符。

3.使用一個哈希集合來跟蹤當前窗口中的字符，當遇到重複字符時，將left指針向右移動以移除重複字符。

**Plan**

1.初始化left指針為0，right指針為0，並初始化一個集合char_set來存儲當前窗口中的字符。

2.遍歷字符串 s，使用 right 指針來擴展窗口。
  
  ．如果當前字符不在集合中，將其添加到集合中，並更新最長子字串的長度。
  
  ．如果當前字符已經在集合中，則不斷收縮窗口，直到該字符被移除，這時候更新 left 指針的值。

3.返回最長子字串的長度。

**Implement**

see solution.py

**Review**

回顧滑動窗口和集合的解法是否充分解決了無重複字符子串的需求。具體來說，確認：

．左右指針的移動是否能涵蓋所有情況；

．集合處理重複字符的方式是否正確。 此外，考慮是否還有其他方法可以在邏輯上簡化或提高效率。

**Evaluate**

評估解法是否達到題目要求的時間和空間複雜度。這題的滑動窗口方法實現時間複雜度為 O(n)，其中 n 是字符串長度，因為每個字符最多被訪問兩次，符合高效要求。此外，確認是否有其他可能的改進空間。

