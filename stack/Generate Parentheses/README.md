**Generate Parentheses**
-
🔗 Link: Generate Parentheses

💡 Difficulty: Medium

🛠️ Topics: stack,Recursion (遞迴),Backtracking(回溯)

==================================================================

You are given an integer n. Return all well-formed parentheses strings that you can generate with n pairs of parentheses.

Example 1:

Input: n = 1
Output: ["()"]

Example 2:

Input: n = 3
Output: ["((()))","(()())","(())()","()(())","()()()"]

You may return the answer in any order.

Constraints:

．1 <= n <= 7

======================================================================

**UMPIRE Method**:

**Understand**

你已經正確理解了題目的關鍵點：

．如果 n = 1，生成一對括號，結果是()。

．如果 n = 3，生成三對括號，結果應是不同的排列，如((())), (()())等。

．n 必須是正整數。

．括號必須對稱，意即每個左括號 ( 都需要有對應的右括號 )。

．多對括號可以有不同的排列方法。

**Match**

你正確地選擇了 stack 方法來進行運算，這很符合這類問題，因為堆疊適合處理括號的匹配問題。但對於生成所有合法的括號排列，這更像是一個 回溯（backtracking） 的問題。

**Plan**

這裡我來幫你進一步擴展思路：

1.設置變量：你需要兩個變量來追蹤已經使用的左括號和右括號的數量。這樣能確保生成的是有效的括號組合。

．open_count：已經放置的左括號 ( 數量。

．close_count：已經放置的右括號 ) 數量。

2.回溯：使用遞迴（recursion）去嘗試每種可能的組合。當條件滿足時，將結果存入一個結果集。

．只要 open_count 小於 n，你就可以放置更多的左括號。

．只要 close_count 小於 open_count，你就可以放置右括號。

3.結束條件：當左右括號的數量都等於 n，說明已經生成了一個有效的括號組合。

**Implement**

see solution.py

**Review**

根據具體需求，我們可以進一步優化或測試程式的效率與表現。例如，測試 n=1, n=3，甚至更大的值。

**Evaluate**

檢查生成的結果是否符合要求：

．每組括號數量是否等於 n。

．括號是否對稱且合法。

．性能是否在合理範圍內。

小結：

．你的思路方向是正確的，堆疊是用來檢查括號是否配對正確的好工具，但在這個題目中，我們更傾向於使用**遞迴（backtracking）**來生成所有的可能組合。

．可以考慮將問題的重點放在回溯算法上，通過控制左右括號的放置來確保結果是合法的。
