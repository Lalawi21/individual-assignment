# individual-assignment
# Name Lalawit teferi
# Id 4473/23
# Time Complexity Analysis:
README for Finding Smallest, Second Largest, and Third Largest Elements in an Array
Finding Smallest, Second Largest, and Third Largest Elements in an Array
 aims to implement algorithms that find the smallest element, the second largest element, and the third largest element in a list or array. The goal is to provide clear and efficient solutions for each problem, along with explanations of the approach and time complexity.


Find the Smallest Element: An algorithm to find the smallest element in the list/array.

Find the Second Largest Element: An algorithm to find the second largest element in the list/array.

Find the Third Largest Element: An algorithm to find the third largest element in the list/array.

Time and Space Complexity: Analysis of the time and space complexities for each algorithm.
Find the Smallest Element in an Array
Algorithm
Start by assuming the first element is the smallest.

Traverse the entire array, and for each element, compare it with the current smallest value.
The pointer sorting algorithm is a concept that involves sorting using pointers to represent the data rather than directly manipulating the data itself. The focus of this project is to implement the pointer sorting technique using several well-known sorting algorithms. By analyzing these algorithms, we can understand their theoretical and empirical performance in the context of pointer-based sorting.
Find the Second Largest Element in an Array
Algorithm
Initialize two variables: largest and second_largest to the smallest possible values.

Traverse the array:

If the current element is greater than largest, update second_largest to largest, and then update largest to the current element.

If the current element is greater than second_largest but less than largest, update second_largest.

Return second_largest.
Find the Third Largest Element in an Array
Algorithm
Initialize three variables: first, second, and third to the smallest possible values.

Traverse the array:

If the current element is greater than first, update third to second, second to first, and first to the current element.

If the current element is greater than second but less than first, update third to second and second to the current element.

If the current element is greater than third but less than second, update third.

Return third.
Complexity Analysis
Finding the Smallest Element:

Time Complexity: O(n), where n is the size of the array (linear scan through the array).

Space Complexity: O(1), as we only store the smallest element.

Finding the Second Largest Element:

Time Complexity: O(n), as we make a single pass through the array to find both the largest and second largest elements.

Space Complexity: O(1), only storing the two largest values.

Finding the Third Largest Element:

Time Complexity: O(n), as we traverse the array once to find the three largest elements.

Space Complexity: O(1), as we only store the three largest values.

Summary
Smallest Element: The smallest element can be found by iterating through the array once and keeping track of the smallest value.

Second Largest Element: The second largest element can be found in one pass by tracking the largest and second largest elements during the traversal.

Third Largest Element: Similar to finding the second largest, we can track the three largest elements as we traverse the array.

For all three problems, the time complexity is O(n), and the space complexity is O(1), making them very efficient in terms of memory usage.


Complexity Analysis
For each sorting algorithm, we analyze the time and space complexity:

Time Complexity: The number of comparisons and swaps performed by each algorithm.

Space Complexity: The amount of additional memory used by the algorithm, considering pointer manipulation.
Time Complexities
Bubble Sort: O(n²)
insertion Sort: O(n²)
Space Complexities
Bubble Sort: O(1) (in-place)
Insertion Sort: O(1) (in-place)
Performance Comparison
Performance comparisons are carried out by testing the algorithms on random data sets of varying sizes. The execution times are measured and plotted for each algorithm. The results give an insight into how the algorithms scale with the input size.

The following results are compared:

Execution Time: Measured in seconds for each algorithm.

Input Size: Varying from small to large arrays.

Execution Graphs: Visualization of execution time vs. input size.

Summary of Findings
Best Performance: Merge Sort, Quick Sort, and Heap Sort generally offer the best performance for large datasets due to their O(n log n) time complexity.

Worst Performance: Bubble Sort and Insertion Sort are inefficient for larger datasets, with time complexities of O(n²).

Space Efficiency: Bubble Sort, Insertion Sort, and Heap Sort are the most space-efficient, requiring only O(1) additional space.

Practical Use Cases: For small datasets, Insertion Sort might be faster in practice despite its O(n²) time complexity due to low overhead. For larger datasets, Merge Sort and Quick Sort are preferable.
Binary Search: Iterative vs Recursive Approach
Key Features:
Binary Search: Implemented using both iterative and recursive approaches.

Complexity Analysis: Comparison of time and space complexity for both iterative and recursive approaches.

Performance Evaluation: Empirical performance comparison between both approaches.

Summary of Findings: Discuss the practical advantages and disadvantages of iterative vs recursive solution

Algorithms can be implemented in different ways, and two common approaches are iterative and recursive. An iterative approach uses loops (such as for or while loops) to perform repetitive tasks, while a recursive approach involves a function calling itself to solve smaller instances of the same problem.

In this project, we implement the Binary Search algorithm using both iterative and recursive methods to compare their time and space complexities, and evaluate which approach is more efficient in different scenarios.

Binary Search Overview
Binary Search is a classic algorithm used to find the position of a target value within a sorted array. It works by repeatedly dividing the search interval in half:

If the value of the target is less than the value in the middle of the interval, the search continues in the lower half.

If the value of the target is greater than the value in the middle of the interval, the search continues in the upper half.

The process repeats until the target is found or the search interval is empty.

Binary Search operates in O(log n) time complexity, making it efficient for large datasets.

Iterative Approach
In the iterative approach, we use a while loop to repeatedly narrow down the search interval based on comparisons.

Iterative Binary Search Implementation
def binary_search_iterative(arr, target):
    left, right = 0, len(arr) - 1
    
    while left <= right:
        mid = left + (right - left) // 2
        
        if arr[mid] == target:
            return mid  # Target found
        elif arr[mid] < target:
            left = mid + 1  # Search in the right half
        else:
            right = mid - 1  # Search in the left half
    
    return -1  # Target not found
Recursive Approach
In the recursive approach, the function calls itself with a smaller search interval until the target is found or the search interval becomes empty.

Recursive Binary Search Implementation
def binary_search_recursive(arr, target, left, right):
    if left <= right:
        mid = left + (right - left) // 2
        
        if arr[mid] == target:
            return mid  # Target found
        elif arr[mid] < target:
            return binary_search_recursive(arr, target, mid + 1, right)  # Search in the right half
        else:
            return binary_search_recursive(arr, target, left, mid - 1)  # Search in the left half
    else:
        return -1  # Target not found
Wrapper Function for Recursive Binary Search
def binary_search(arr, target):
    return binary_search_recursive(arr, target, 0, len(arr) - 1)
Complexity Analysis
Time Complexity:
Iterative Approach: Both approaches, iterative and recursive, perform the same number of comparisons in the worst case. The time complexity is O(log n) for both methods because we reduce the search space by half at each step.

Recursive Approach: Also has O(log n) time complexity, but recursion introduces function call overhead. In the worst case, there are log n recursive calls.

Space Complexity:
Iterative Approach: The space complexity is O(1) because only a few variables (like left, right, and mid) are used, regardless of the size of the input.

Recursive Approach: The space complexity is O(log n) because of the recursion stack. Each recursive call adds a frame to the stack, which can grow up to log n calls in the worst case.

Performance Comparison
Both the iterative and recursive approaches perform similarly in terms of time complexity, as both are O(log n). However, the space complexity differs:

Iterative Approach: More space-efficient, using only a constant amount of memory (O(1)).

Recursive Approach: Uses more memory due to the function call stack, leading to O(log n) space complexity.

Empirical Comparison
The performance is measured using arrays of increasing sizes to observe any significant differences in runtime. For practical purposes, the iterative approach is usually faster in real-world scenarios due to the overhead of function calls in recursion. However, for very small datasets, the recursive approach can sometimes be simpler and more elegant to implement.

Summary of Findings
Time Complexity: Both iterative and recursive approaches have the same time complexity O(log n), making them equally efficient in terms of runtime.

Space Complexity: The iterative approach is more space-efficient (O(1)), while the recursive approach uses O(log n) space due to the recursion stack.

Practical Considerations: The iterative approach is generally preferred for larger datasets due to its lower space complexity and avoidance of recursion overhead. The recursive approach can be more elegant and easier to implement for small or simple problems.

Exponential Search, Jump Search, and Hashing-based Searching Algorithms
In this overview, we will explain three searching algorithms—Exponential Search, Jump Search, and Hashing-based Searching—how they work, their complexity analysis, and provide implementations in C++. After that, we will summarize the findings and discuss the advantages and disadvantages of each algorithm.

1. Exponential Search
How It Works: Exponential Search is a searching algorithm that works on sorted arrays. It combines binary search with an exponential step to quickly locate an element. The idea behind exponential search is to find a range where the element might exist and then perform a binary search within that range.

Exponentially increase the index from 1, 2, 4, 8, 16, etc., until the target value is greater than the current element in the array.

Once the range is found, perform a binary search within that range.

Time Complexity:

Best case: O(1) (if the element is found at the first check).

Worst case: O(log n), as you may have to search over the entire array logarithmically.

Space Complexity:

O(1) because it only uses a constant amount of extra space.
2. Jump Search
How It Works: Jump Search is designed for ordered (sorted) lists. The basic idea is to divide the list into blocks (of size √n), and then jump through the blocks to find the range where the target element may be present. Once a block is found, linear search is performed within the block.

Calculate the block size as √n.

Jump forward by √n steps at a time until a block is found where the target might lie.

Once the block is found, use linear search to find the target within the block.

Time Complexity:

Best case: O(1) (if the element is found in the first block).

Worst case: O(√n), as you may need to jump through the array in blocks and perform a linear search inside one block.

Space Complexity:O(1) because it only uses a constant amount of extra space.
3. Hashing-based Searching
How It Works: Hashing is a technique where we store key-value pairs in a data structure called a hash table. It uses a hash function to convert the key into an index in an array, where the value is stored. Hashing allows constant time complexity for searching, insertion, and deletion (on average).

A hash function is used to map the key to an index.

The value is stored at the computed index in the hash table.

To search, the hash function computes the index, and the value is retrieved in constant time, O(1).

Time Complexity:

Best case: O(1), if there are no collisions.

Worst case: O(n), if all elements hash to the same index (collision), resulting in a list at each index.

Space Complexity:

O(n) because we store n elements in the hash table.
Summary of Findings
Exponential Search:

Time Complexity: O(log n) in the worst case.

Space Complexity: O(1).

Best Used For: Sorted arrays, especially when the array is large but the element’s position is unknown and the range is exponentially increasing.

Jump Search:

Time Complexity: O(√n) in the worst case.

Space Complexity: O(1).

Best Used For: Sorted arrays with large data sizes where jumping through blocks can minimize the number of elements to check.

Hashing-based Search:

Time Complexity: O(1) on average, O(n) in the worst case.

Space Complexity: O(n).
Each of these searching algorithms offers different advantages based on the dataset characteristics, such as size and order. For sorted arrays, Exponential Search and Jump Search provide efficient ways to search in less time than traditional linear search. Hashing-based Search, on the other hand, provides near constant-time search capabilities, making it ideal for large datasets with random access.

