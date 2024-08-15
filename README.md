# 12-1
*This is a homework assignment for Coding Temple.

Data Structures And Algorithms Fundamentals

Backend Specialization / Module 12 Lesson 1 Assignment: Data Structures And Algorithms Fundamentals

Author: Reggie Joseph

Case Study: Optimizing Text Messaging App with Efficient Data Structures

For an application that handles the storage and retrieval of messages, two big factors to consider is how new messages are inserted and how old messages are accessed.

New messages could be added in large quantities, and it only makes sense to store messages in the order they have been received. To this end, it does not make a lot of sense to store messages in a linked list, as we would not have a need to insert messages before any other messages, nor in a binary tree, as new messages would only ever be inserted to the right of older messages. An array could keep the messages all in the order they were received, and a stack would make it easy to access the most recent messages, as most users would reasonably want to do.

Hash tables are one of the best data structures for search complexity, as they can quickly access data given a unique key. However, this would not help with a message system, as multiple messages could be received from the same sender, message bodies could be identical, and users will not reasonably be able to remember the exact date and time a message was received. So without a memorable unique key with which users could search, an unordered dictionary is not a practical way of retrieving information.

For both these reasons, we want a linear, dynamic data structure, so I think that a stack would be among the more favorable options. Adding new messages would have a constant time and space complexity, and searching for messages would have a linear time complexity and a constant space complexity; and again, the most recent messages are likely going to be accessed the most frequently.

When considering using long polling or WebSockets as a technique for real-time communication between client and server, WebSockets allows for more efficient, low-latency, high-volume, two-way communication. The ability to handle high volumes of messages with quick responsiveness is very important in our increasingly online world.


Case Study: Analyzing Big O Complexity for a Sorting Algorithm

def simple_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
This algorithm takes in an array, then iterates through that array at index of i. In a nested loop, every value (j) before i is compared to the value following j (j+1). If j is greater than j+1, the values are swapped. When the entire list has been iterated through, the array will be sorted, with the smallest value at index 0, and the greatest value at the end of the array. I believe this is an insertion sort.

The double for loop creates a time complexity of O(n²). Each time the first loop runs, the second runs within it. The space complexity is constant, as it takes in only one array and the data does not change, but the quadratic time complexity is considered a horrible complexity, and this algorithm would run slowly with large datasets.

There are mutliple algorithms that could sort through the array with better time complexity, such as Mergesort, Timsort, or Counting Sort, though they would also give us worse space complexity. Heapsort is an algoritm that would give us better time complexity (O(n log(n))), while also maintaining a constant space complexity.
