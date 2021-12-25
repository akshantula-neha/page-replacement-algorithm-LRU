# page-replacement-algorithm-LRU

**Page replacement algorithm:**

In an operating system that uses paging for memory management, a page replacement algorithm is needed to decide which page needs to be replaced when new page comes in. Page Fault – A page fault happens when a running program accesses a memory page that is mapped into the virtual address space, but not loaded in physical memory. Since actual physical memory is much smaller than virtual memory, page faults happen. In case of page fault, Operating System might have to replace one of the existing pages with the newly needed page. Different page replacement algorithms suggest different ways to decide which page to replace. The target for all algorithms is to reduce the number of page faults.

**LRU-Least Recently Used :**

LRU policy follows the concept of locality of reference as the base for its page replacement decisions. LRU policy says that pages that have not been used for the longest period of time will probably not be used for a long time. So, when a page fault occurs, it is better to replace the page that has been unused for a long time. This strategy is called LRU (Least Recently Used) paging. LRU policy is often used as a page replacement algorithm and considered to be good

**Advantages :**

It is open for full analysis. In this, we replace the page which is least recently used, thus free from Belady’s Anomaly. Easy to choose page which has faulted and hasn’t been used for a long time.

**Disadvantage :**

The problem is to determine an order for the frames defined by the time of last use. So, implementing LRU will require extra overhead either software implementation with extra computational time or implementation by hardware. To implement LRU we can use a linked list of all pages in memory, with the most recent page at the font and the least recent page at the rare. So, update deletion and insertion of linked lists is a time-consuming operation. Another way to implement LRU is special hardware either counter or stack.

**Algorithm :**

Let capacity be the number of pages that memory can hold. Let set be the current set of pages in memory.

1- Start traversing the pages. 
 i) If set holds less pages than capacity.
  a) Insert page into the set one by one until the size of set reaches capacity or all page requests are processed. 
  b) Simultaneously maintain the recent occurred index of each page in a map called indexes. 
  c) Increment page fault
 ii) Else If current page is present in set, do nothing. 
     Else 
  a) Find the page in the set that was least recently used. We find it using index array. We basically need to replace the page with minimum index. 
  b) Replace the found page with current page. 
  c) Increment page faults. 
  d) Update index of current page.

2-Return page faults.

**Example :**

Sample String : 0 4 1 4 2 4 3 4 2 4 0 4

<img width="580" alt="GITHUB2" src="https://user-images.githubusercontent.com/90513459/147381141-1030b814-961f-4f5b-b8a0-2314622fd341.png">

**OUTPUT:**
![Screenshot (4)](https://user-images.githubusercontent.com/90513459/147380774-55a36e1e-cab9-4a2c-8816-254fd54e4311.png)
