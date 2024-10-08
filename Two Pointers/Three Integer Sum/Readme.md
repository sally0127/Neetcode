**Three Integer Sum**
-
🔗 Link: Three Integer Sum(https://neetcode.io/problems/three-integer-sum)

💡 Difficulty: Medium

🛠️ Topics: Array, Two Pointers,Combination

======================================================================

Given an integer array nums, return all the triplets [nums[i], nums[j], nums[k]] where nums[i] + nums[j] + nums[k] == 0, and the indices i, j and k are all distinct.

The output should not contain any duplicate triplets. You may return the output and the triplets in any order.

Example 1:

Input: nums = [-1,0,1,2,-1,-4]

Output: [[-1,-1,2],[-1,0,1]]

Explanation:

nums[0] + nums[1] + nums[2] = (-1) + 0 + 1 = 0.

nums[1] + nums[2] + nums[4] = 0 + 1 + (-1) = 0.

nums[0] + nums[3] + nums[4] = (-1) + 2 + (-1) = 0.

The distinct triplets are [-1,0,1] and [-1,-1,2].

Example 2:

Input: nums = [0,1,1]

Output: []

Explanation: The only possible triplet does not sum up to 0.

Example 3:

Input: nums = [0,0,0]

Output: [[0,0,0]]

Explanation: The only possible triplet sums up to 0.

Constraints:

．3 <= nums.length <= 1000

．-10^5 <= nums[i] <= 10^5

=================================================================================

**UMPIRE Method**:

**Understand**

．Three values sum to zero: This is completely correct; the goal is to find three integers whose sum equals zero.

．The three values cannot be duplicated: This is also correct since i, j, and k must be distinct indices.

．Do the three values need to be in order? Your question here is whether the order of the three values matters. In fact, the order of these three numbers is not important in the output, but you need to ensure that the result does not contain duplicate triplets (for example, [a, b, c] and [c, b, a] are considered duplicates).

**Match**

．Two-Pointer Method: You fully understand this technique. After sorting the array, you can use two pointers for each nums[i] to find the other two numbers. This is the most efficient method with a time complexity of O(n²).

．Conditions for the answer: When the sum of three numbers equals zero, you can directly record the result.

．Pointer operations: You mentioned left and right pointers, which is correct. You can move the pointers based on the current sum to adjust the total.

**Plan**

．Sort the array: First, sort nums so that we can effectively use the two-pointer method to find the triplets.

．Traverse the array: For each nums[i], use two pointers, left and right, starting from i+1 and n-1, respectively.

．Calculate the sum:
 ． When nums[i] + nums[left] + nums[right] == 0, record this triplet.
 ． If the sum is less than 0, move the left pointer to the right to increase the total.
 ． If the sum is greater than 0, move the right pointer to the left to decrease the total.

．Deduplication: After finding a triplet, to avoid duplicate triplets, skip the same numbers. For example, if nums[i] is the same as the previous number, skip it.

．End: Repeat the above steps until the entire array is traversed.

**Implement**

see solution.py

**Review**

．Minimum case: The minimum case for the array is a length of 3, which this code can handle.

．All elements are the same: When all elements are the same or very similar, the code skips duplicate results, thus avoiding multiple calculations of the same triplet.

．There are no triplets in the array that sum to zero: The code will ultimately return an empty result, which also handles this case correctly.

**Evaluate**

．Time complexity: The time to sort the array is O(n log n), and the two-pointer method runs in O(n) for each element, so the total time complexity is O(n²).

．Space complexity: The algorithm uses constant space to store pointers and results, so the space complexity is O(1), even though the results store the found triplets.


