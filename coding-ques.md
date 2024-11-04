# Software Engineer I - Technical Interview Questions
## Evaluation Matrix

### Scoring Guidelines (Per Question):
- Problem Understanding: 0-3 points
  - 3: Complete understanding
  - 2: Good understanding with minor clarifications needed
  - 1: Partial understanding, needed significant clarification
  - 0: Did not understand the problem

- Technical Solution: 0-5 points
  - 5: Optimal solution with proper explanation
  - 4: Correct solution with good optimization
  - 3: Working solution but not optimized
  - 2: Partially correct solution
  - 1: Attempted but incorrect solution
  - 0: No valid solution attempted

- Code Quality: 0-2 points
  - 2: Clean, well-structured code with good naming
  - 1: Functional but messy code
  - 0: Poor code quality or no code written

### Overall Rating Scale:
- Easy Question: 10 points max
- Medium Question: 10 points max
- Hard Question: 10 points max
Total Possible Score: 30 points

Recommended Passing Criteria:
- Strong Pass: 24-30 points
- Pass: 18-23 points
- Weak Pass: 15-17 points
- Fail: Below 15 points

## Easy Questions (Choose One)

### E1: Two Sum
**Problem Statement:**
Given an array of integers `nums` and an integer `target`, return indices of the two numbers in the array that add up to the target. You may assume that each input would have exactly one solution.

**Example:**
```
Input: nums = [2, 7, 11, 15], target = 9
Output: [0, 1]
Explanation: Because nums[0] + nums[1] == 9
```

**Solution:**
```python
def two_sum(nums, target):
    num_dict = {}
    for i, num in enumerate(nums):
        complement = target - num
        if complement in num_dict:
            return [num_dict[complement], i]
        num_dict[num] = i
    return []

# Time Complexity: O(n)
# Space Complexity: O(n)
```

**Key Points to Evaluate:**
- Did they ask about input constraints?
- Did they consider using a hash map for O(n) solution?
- Did they handle edge cases?

### E2: Valid Parentheses
**Problem Statement:**
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid. The string is valid if all brackets are closed in the correct order.

**Example:**
```
Input: s = "()[]{}"
Output: true
Input: s = "([)]"
Output: false
```

**Solution:**
```python
def is_valid_parentheses(s):
    stack = []
    pairs = {')': '(', '}': '{', ']': '['}
    
    for char in s:
        if char in '({[':
            stack.append(char)
        elif char in ')}]':
            if not stack or stack.pop() != pairs[char]:
                return False
    
    return len(stack) == 0

# Time Complexity: O(n)
# Space Complexity: O(n)
```

## Medium Questions (Choose One)

### M1: Binary Tree Level Order Traversal
**Problem Statement:**
Given the root of a binary tree, return the level order traversal of its nodes' values (i.e., from left to right, level by level).

**Example:**
```
Input: root = [3,9,20,null,null,15,7]
Output: [[3],[9,20],[15,7]]
```

**Solution:**
```python
from collections import deque

class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def level_order_traversal(root):
    if not root:
        return []
        
    result = []
    queue = deque([root])
    
    while queue:
        level_size = len(queue)
        current_level = []
        
        for _ in range(level_size):
            node = queue.popleft()
            current_level.append(node.val)
            
            if node.left:
                queue.append(node.left)
            if node.right:
                queue.append(node.right)
                
        result.append(current_level)
    
    return result

# Time Complexity: O(n)
# Space Complexity: O(n)
```

### M2: Longest Substring Without Repeating Characters
**Problem Statement:**
Given a string s, find the length of the longest substring without repeating characters.

**Example:**
```
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.
```

**Solution:**
```python
def length_of_longest_substring(s):
    char_index = {}
    max_length = 0
    start = 0
    
    for end, char in enumerate(s):
        if char in char_index and char_index[char] >= start:
            start = char_index[char] + 1
        else:
            max_length = max(max_length, end - start + 1)
        char_index[char] = end
    
    return max_length

# Time Complexity: O(n)
# Space Complexity: O(min(m,n)) where m is the size of the character set
```

## Hard Questions (Choose One)

### H1: Merge K Sorted Lists
**Problem Statement:**
Given an array of k linked-lists lists, each linked-list is sorted in ascending order. Merge all the linked-lists into one sorted linked-list and return it.

**Example:**
```
Input: lists = [[1,4,5],[1,3,4],[2,6]]
Output: [1,1,2,3,4,4,5,6]
```

**Solution:**
```python
import heapq

class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def merge_k_lists(lists):
    # Initialize min-heap
    heap = []
    
    # Add first node from each list to heap
    for i, lst in enumerate(lists):
        if lst:
            heapq.heappush(heap, (lst.val, i, lst))
    
    dummy = ListNode(0)
    current = dummy
    
    # Process nodes from heap
    while heap:
        val, i, node = heapq.heappop(heap)
        current.next = node
        current = current.next
        
        if node.next:
            heapq.heappush(heap, (node.next.val, i, node.next))
    
    return dummy.next

# Time Complexity: O(N*log(k)) where N is total number of nodes and k is number of lists
# Space Complexity: O(k)
```

### H2: Trapping Rain Water
**Problem Statement:**
Given n non-negative integers representing an elevation map where the width of each bar is 1, compute how much water it can trap after raining.

**Example:**
```
Input: height = [0,1,0,2,1,0,1,3,2,1,2,1]
Output: 6
```

**Solution:**
```python
def trap(height):
    if not height:
        return 0
        
    left, right = 0, len(height) - 1
    left_max = right_max = water = 0
    
    while left < right:
        if height[left] < height[right]:
            if height[left] >= left_max:
                left_max = height[left]
            else:
                water += left_max - height[left]
            left += 1
        else:
            if height[right] >= right_max:
                right_max = height[right]
            else:
                water += right_max - height[right]
            right -= 1
    
    return water

# Time Complexity: O(n)
# Space Complexity: O(1)
```

## Interview Guidelines

### Time Management:
- Easy Question: 15-20 minutes
- Medium Question: 25-30 minutes
- Hard Question: 35-40 minutes

### What to Look For:
1. Problem-Solving Approach:
   - Asks clarifying questions
   - Discusses multiple approaches
   - Explains trade-offs

2. Technical Skills:
   - Proper use of data structures
   - Time/space complexity understanding
   - Code optimization

3. Communication:
   - Clear explanation of thought process
   - Good code documentation
   - Professional interaction

4. Testing:
   - Considers edge cases
   - Writes test cases
   - Debugging approach

### Red Flags:
- Unable to solve easy question
- Poor understanding of time/space complexity
- No testing/edge case consideration
- Inability to explain approach
- Poor code quality/style

### Green Flags:
- Clean, efficient code
- Strong problem-solving methodology
- Good communication
- Proper error handling
- Optimization considerations





# Software Engineer I - Technical Interview Questions
## Evaluation Matrix

### Scoring Guidelines (Per Question):
- Problem Understanding: 0-3 points
  - 3: Complete understanding
  - 2: Good understanding with minor clarifications needed
  - 1: Partial understanding, needed significant clarification
  - 0: Did not understand the problem

- Technical Solution: 0-5 points
  - 5: Optimal solution with proper explanation
  - 4: Correct solution with good optimization
  - 3: Working solution but not optimized
  - 2: Partially correct solution
  - 1: Attempted but incorrect solution
  - 0: No valid solution attempted

- Code Quality: 0-2 points
  - 2: Clean, well-structured code with good naming
  - 1: Functional but messy code
  - 0: Poor code quality or no code written

### Overall Rating Scale:
- Easy Question: 10 points max
- Medium Question: 10 points max
- Hard Question: 10 points max
Total Possible Score: 30 points

Recommended Passing Criteria:
- Strong Pass: 24-30 points
- Pass: 18-23 points
- Weak Pass: 15-17 points
- Fail: Below 15 points

## Easy Questions (Choose One)

### E1: Circular Printer
**Problem Statement:**
You have a circular printer wheel with lowercase English letters 'a' to 'z' arranged clockwise. Initially, the printer points to 'a'. Moving from any character to any adjacent character takes 1 second. You can move either clockwise or counterclockwise. Given a string s, return the minimum time needed to print the string.

**Example:**
```
Input: s = "cat"
Output: 7
Explanation: 
'a' -> 'c': 2 moves counterclockwise
'c' -> 'a': 2 moves clockwise
'a' -> 't': 3 moves counterclockwise
Total: 7 moves
```

**Solution:**
```python
def min_time_to_print(s):
    current = 'a'
    total_time = 0
    
    for char in s:
        # Calculate clockwise and counterclockwise distances
        dist1 = abs(ord(char) - ord(current))
        dist2 = 26 - dist1
        
        # Take minimum of clockwise and counterclockwise distances
        total_time += min(dist1, dist2)
        current = char
    
    return total_time

# Time Complexity: O(n)
# Space Complexity: O(1)
```

**Key Points to Evaluate:**
- Did they recognize the circular nature of the problem?
- Did they consider both clockwise and counterclockwise movements?
- Did they handle wrapping around the wheel efficiently?

### E2: Alternating Digit Sum
**Problem Statement:**
Given a positive integer n, calculate the alternating sum of its digits. Starting from the leftmost digit, add and subtract consecutive digits.

**Example:**
```
Input: n = 521
Output: 0
Explanation: 5 - 2 + 1 = 0

Input: n = 111
Output: 1
Explanation: 1 - 1 + 1 = 1
```

**Solution:**
```python
def alternating_sum(n):
    # Convert to string for easy digit access
    digits = str(n)
    total = 0
    
    for i in range(len(digits)):
        digit = int(digits[i])
        # Alternate between adding and subtracting
        if i % 2 == 0:
            total += digit
        else:
            total -= digit
            
    return total

# Time Complexity: O(log n) - number of digits
# Space Complexity: O(log n)
```

## Medium Questions (Choose One)

### M1: Consecutive Array Construction
**Problem Statement:**
Given an array of integers, determine if it's possible to split it into two non-empty subarrays such that the first subarray contains consecutive integers (in any order) and the second subarray contains the remaining elements.

**Example:**
```
Input: [1, 3, 4, 2, 7, 8]
Output: true
Explanation: Can split into [1, 3, 4, 2] and [7, 8]
First subarray contains consecutive numbers 1,2,3,4

Input: [3, 4, 7, 1, 8, 2]
Output: false
```

**Solution:**
```python
def can_split_consecutive(arr):
    if len(arr) < 2:
        return False
        
    def is_consecutive(sub_arr):
        if not sub_arr:
            return False
        min_val = min(sub_arr)
        max_val = max(sub_arr)
        return set(range(min_val, max_val + 1)) == set(sub_arr)
    
    # Try different split points
    for i in range(1, len(arr)):
        first = arr[:i]
        second = arr[i:]
        if is_consecutive(first) or is_consecutive(second):
            return True
            
    return False

# Time Complexity: O(n^2)
# Space Complexity: O(n)
```

### M2: Document Version Compare
**Problem Statement:**
You're building a document versioning system. Given two version strings containing lowercase letters and dots (.), determine if they represent the same document content. A single dot means "keep this character from the previous version", and multiple consecutive dots mean "keep multiple characters". Return true if both strings represent the same content.

**Example:**
```
Input: version1 = "abc", version2 = "a.c"
Output: false

Input: version1 = "programming", version2 = "p...ram..ng"
Output: true
Explanation: p...ram..ng represents "programming"
```

**Solution:**
```python
def are_versions_same(version1, version2):
    def expand_version(version, reference):
        if not reference:
            return version.replace('.', '')
            
        result = []
        ref_idx = 0
        
        for char in version:
            if char == '.':
                if ref_idx >= len(reference):
                    return None  # Invalid version
                result.append(reference[ref_idx])
                ref_idx += 1
            else:
                result.append(char)
                ref_idx += 1
                
        return ''.join(result)
    
    # Try expanding both versions using each other as reference
    expanded1 = expand_version(version2, version1)
    expanded2 = expand_version(version1, version2)
    
    return expanded1 == version1 or expanded2 == version2

# Time Complexity: O(n)
# Space Complexity: O(n)
```

## Hard Questions (Choose One)

### H1: Network Delay Optimizer
**Problem Statement:**
You have a network of servers represented as a directed graph. Each edge has a transmission time and a cost. Given a source server, a destination server, and a maximum cost K, find the minimum transmission time possible while keeping the total cost under K.

**Example:**
```
Input: 
nodes = 4
edges = [(0,1,2,5), (0,2,4,3), (1,2,1,2), (2,3,3,4)]  # (from, to, time, cost)
source = 0
destination = 3
max_cost = 8
Output: 6
Explanation: Path 0->1->2->3 with total time 6 and cost 7
```

**Solution:**
```python
from collections import defaultdict
import heapq

def min_transmission_time(nodes, edges, source, destination, max_cost):
    # Build adjacency list
    graph = defaultdict(list)
    for u, v, time, cost in edges:
        graph[u].append((v, time, cost))
    
    # Priority queue: (total_time, total_cost, node)
    pq = [(0, 0, source)]
    # Keep track of best time for each node at each cost
    seen = defaultdict(lambda: float('inf'))
    
    while pq:
        time, cost, node = heapq.heappop(pq)
        
        if node == destination:
            return time
            
        for next_node, t, c in graph[node]:
            new_time = time + t
            new_cost = cost + c
            
            if new_cost > max_cost:
                continue
                
            if new_time < seen[(next_node, new_cost)]:
                seen[(next_node, new_cost)] = new_time
                heapq.heappush(pq, (new_time, new_cost, next_node))
    
    return -1

# Time Complexity: O(E * K * log(V*K)) where E is edges, V is vertices, K is max_cost
# Space Complexity: O(V * K)
```

### H2: Dynamic Data Stream Analyzer
**Problem Statement:**
Design a data structure that supports analyzing a stream of integers with the following operations:
1. add(num): Add a number to the stream
2. removeRange(start, end): Remove all numbers in the range [start, end]
3. queryAverage(k): Return the average of the last k remaining numbers in the stream

All operations should work in O(log n) time complexity.

**Example:**
```
Input:
["StreamAnalyzer"]
add(1)
add(2)
add(3)
queryAverage(2)  # returns 2.5
removeRange(1, 2)
queryAverage(1)  # returns 3.0
```

**Solution:**
```python
from sortedcontainers import SortedList

class StreamAnalyzer:
    def __init__(self):
        self.numbers = SortedList()
        self.sum_window = 0
        
    def add(self, num):
        self.numbers.add(num)
        self.sum_window += num
        
    def removeRange(self, start, end):
        # Find indices of range boundaries
        start_idx = self.numbers.bisect_left(start)
        end_idx = self.numbers.bisect_right(end)
        
        # Remove numbers and update sum
        for num in self.numbers[start_idx:end_idx]:
            self.sum_window -= num
        
        self.numbers.difference_update(
            self.numbers[start_idx:end_idx]
        )
        
    def queryAverage(self, k):
        if k > len(self.numbers):
            return 0
            
        window_sum = sum(self.numbers[-k:])
        return window_sum / k

# Time Complexity: 
# add: O(log n)
# removeRange: O(k log n) where k is numbers in range
# queryAverage: O(k)
# Space Complexity: O(n)
```

## Interview Guidelines

### Time Management:
- Easy Question: 15-20 minutes
- Medium Question: 25-30 minutes
- Hard Question: 35-40 minutes

### What to Look For:
1. Problem-Solving Approach:
   - Asks clarifying questions
   - Discusses multiple approaches
   - Explains trade-offs

2. Technical Skills:
   - Proper use of data structures
   - Time/space complexity understanding
   - Code optimization

3. Communication:
   - Clear explanation of thought process
   - Good code documentation
   - Professional interaction

4. Testing:
   - Considers edge cases
   - Writes test cases
   - Debugging approach

### Red Flags:
- Unable to solve easy question
- Poor understanding of time/space complexity
- No testing/edge case consideration
- Inability to explain approach
- Poor code quality/style

### Green Flags:
- Clean, efficient code
- Strong problem-solving methodology
- Good communication
- Proper error handling
- Optimization considerations

### Follow-up Questions for Each Problem:

#### Easy Questions:
- E1 (Circular Printer):
  - How would you modify the solution if some letters appeared multiple times on the wheel?
  - What if the wheel had different costs for clockwise vs counterclockwise movement?

- E2 (Alternating Digit Sum):
  - How would you handle negative numbers?
  - Can you solve it without converting to string?

#### Medium Questions:
- M1 (Consecutive Array Construction):
  - Can you optimize the solution to O(n log n)?
  - How would you handle duplicate numbers?

- M2 (Document Version Compare):
  - How would you handle multiple versions in sequence?
  - What if dots could represent different numbers of characters?

#### Hard Questions:
- H1 (Network Delay Optimizer):
  - How would you modify the solution for undirected graphs?
  - What if we needed to find all paths under the cost limit?

- H2 (Dynamic Data Stream Analyzer):
  - How would you handle concurrent operations?
  - Can you optimize the memory usage for large streams?
 

Statement
For the given stream of message requests and their timestamps as input, you must implement a logger rate limiter system that decides whether the current message request is displayed. The decision depends on whether the same message has already been displayed in the last SS seconds. If yes, then the decision is FALSE, as this message is considered a duplicate. Otherwise, the decision is TRUE.
Note: Several message requests, though received at different timestamps, may carry identical messages.
Constraint:
* 1≤ request.length ≤100
* 0≤ timestamp ≤1000
* Timestamps are in ascending order.
* Messages can be written in lowercase or uppercase English alphabets.

__________________________________________

I'll provide both solutions: the Rate Limiter in Java and the Ordered Pairs problem.

Let me explain both solutions:

1. Logger Rate Limiter:
```java
public class LoggerRateLimiter {
    private final Map<String, Integer> messageTimestamps;
```
- Uses HashMap to store message-timestamp pairs
- O(1) time complexity for lookups and updates
- Maintains only the most recent timestamp for each message

2. Ordered Pairs Problem:
The problem asks to find all pairs (i,j) where arr[i] + j = arr[j] + i

Key Insight:
- Rearranging the equation: arr[i] - i = arr[j] - j
- This means we're looking for indices that have the same difference between array value and index

Two Solutions Provided:

a) Brute Force (O(n²)):
```java
public static List<int[]> findOrderedPairs(int[] arr) {
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            if (arr[i] + j == arr[j] + i) {
                result.add(new int[]{i, j});
            }
        }
    }
}
```

b) Optimized Solution (O(n + k) where k is number of pairs):
```java
public static List<int[]> findOrderedPairsOptimized(int[] arr) {
    Map<Integer, List<Integer>> diffMap = new HashMap<>();
    // Group indices by their arr[i] - i value
    for (int i = 0; i < arr.length; i++) {
        int diff = arr[i] - i;
        diffMap.computeIfAbsent(diff, k -> new ArrayList<>()).add(i);
    }
}
```

Key Features:
1. Handles negative numbers
2. Works with duplicates
3. Includes cases where i = j
4. Includes cases where i > j

Test Cases Cover:
1. Basic array
2. Array with duplicates
3. Single element array
4. Negative numbers
5. Performance comparison

Would you like me to:
1. Add more test cases?
2. Explain any specific part in more detail?
3. Add visualization for how the algorithm works?
4. Provide alternative solutions using different data structures?


------------------------------------------------------------------

# Array Index Pairs

## Problem Statement
Given an array of integers, find all ordered pairs of indices (i,j) that satisfy the equation: 
```
arr[i] + j = arr[j] + i
```
where i and j are valid indices in the array. Note that i can be equal to j, and i can be greater than j.

## Examples

### Example 1:
```
Input: arr = [1, 2, 3]
Output: [(0,0), (1,1), (2,2)]
Explanation:
For pair (0,0): arr[0] + 0 = 1 + 0 = 1, arr[0] + 0 = 1 + 0 = 1
For pair (1,1): arr[1] + 1 = 2 + 1 = 3, arr[1] + 1 = 2 + 1 = 3
For pair (2,2): arr[2] + 2 = 3 + 2 = 5, arr[2] + 2 = 3 + 2 = 5
```

### Example 2:
```
Input: arr = [0, 0]
Output: [(0,0), (0,1), (1,0), (1,1)]
Explanation:
For pair (0,0): arr[0] + 0 = 0 + 0 = 0, arr[0] + 0 = 0 + 0 = 0
For pair (0,1): arr[0] + 1 = 0 + 1 = 1, arr[1] + 0 = 0 + 0 = 0
For pair (1,0): arr[1] + 0 = 0 + 0 = 0, arr[0] + 1 = 0 + 1 = 1
For pair (1,1): arr[1] + 1 = 0 + 1 = 1, arr[1] + 1 = 0 + 1 = 1
```

### Example 3:
```
Input: arr = [1]
Output: [(0,0)]
Explanation:
Only one possible pair as there's only one index
```

## Constraints:
* 1 ≤ arr.length ≤ 10^5
* -10^9 ≤ arr[i] ≤ 10^9

## Follow-up Questions:
1. Can you solve it in O(n²) time complexity first?
2. Can you optimize it further?
3. How would you handle memory constraints with a very large input array?
4. How would you modify your solution if we only wanted pairs where i < j?

## Solution Approach Hints:

### Hint 1:
Try rearranging the equation arr[i] + j = arr[j] + i to understand what pairs of indices we're looking for.

### Hint 2:
What can you say about arr[i] - i and arr[j] - j when a pair satisfies the equation?

### Hint 3:
Consider using a hash map to group indices with the same value of arr[i] - i.

## Test Cases to Consider:
```
1. Basic cases:
   Input: [0, 1, 2]
   
2. Array with duplicates:
   Input: [1, 1, 1]
   
3. Negative numbers:
   Input: [-1, -2, -3]
   
4. Single element:
   Input: [5]
   
5. All same elements:
   Input: [2, 2, 2, 2]
```

## Solution Template:
```java
public class Solution {
    public List<int[]> findOrderedPairs(int[] arr) {
        // Your code here
        return new ArrayList<>();
    }
}
```

## Evaluation Criteria:

### Understanding (0-5):
* Problem understanding
* Edge case identification
* Constraint recognition

### Approach (0-5):
* Initial solution strategy
* Optimization ideas
* Time/space complexity analysis

### Implementation (0-5):
* Code correctness
* Code organization
* Error handling

### Testing (0-5):
* Test case coverage
* Edge case handling
* Performance testing

## Common Mistakes to Watch For:
1. Not handling duplicate values correctly
2. Missing self-pairs (i=j)
3. Incorrect handling of negative numbers
4. Not considering array bounds
5. Inefficient implementation for large arrays

## Optimal Solution Complexity:
* Time Complexity: O(n + k) where k is the number of pairs
* Space Complexity: O(n)

## Interview Tips for Candidates:
1. Start with the brute force solution
2. Think about what makes two indices form a valid pair
3. Look for patterns in the arithmetic relationship
4. Consider using a hash map for optimization
5. Don't forget to handle edge cases

## Example Implementation (One Approach):
```java
public List<int[]> findOrderedPairs(int[] arr) {
    List<int[]> result = new ArrayList<>();
    Map<Integer, List<Integer>> diffMap = new HashMap<>();
    
    // Group indices by their arr[i] - i value
    for (int i = 0; i < arr.length; i++) {
        int diff = arr[i] - i;
        diffMap.computeIfAbsent(diff, k -> new ArrayList<>()).add(i);
    }
    
    // Generate pairs from each group
    for (List<Integer> indices : diffMap.values()) {
        for (int i = 0; i < indices.size(); i++) {
            for (int j = 0; j < indices.size(); j++) {
                result.add(new int[]{indices.get(i), indices.get(j)});
            }
        }
    }
    
    return result;
}
```

## Sample Discussion Questions:
1. "How would you verify the correctness of your solution?"
2. "What would be the impact of having mostly duplicate values in the array?"
3. "How would you modify the solution to handle streaming data?"
4. "Can you think of any real-world applications of this problem?"

## Extended Challenges:
1. Find the count of pairs without storing them
2. Return pairs in sorted order
3. Handle very large arrays with limited memory
4. Parallelize the solution for better performance
