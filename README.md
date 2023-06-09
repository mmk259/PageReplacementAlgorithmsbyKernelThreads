# Page Replacement Algorithms by Kernel Threads 

### INTRODUCTION:
Page replacement algorithms are the techniques used to replace the pages in a page frame that are no longer required by the program running in the operating system. These algorithms are used to minimize the number of page faults, which is the situation when a requested page is not found in the memory and needs to be swapped in from disk. This project aims to implement three different page replacement algorithms: First-In-First-Out (FIFO), Optimal, and Least Frequently Used (LFU).

### DESCRIPTION:

The input to the program is taken from a text file containing the reference string, which is the sequence of pages requested by the program. The program reads this file twice, in order to firstly calculate the size of the reference string and secondly to store the reference string in an integer array. The user is then prompted to input the number of frames to be used for page replacement and to choose which algorithm to use.
* **The first algorithm implemented is the _FIFO (First-In, First-Out) rule_.** In this algorithm, the page that has been residing in the memory for the longest duration gets replaced. To facilitate this process, the program creates a temporary array with a size equal to the number of frames, initializing all its elements to 0. For every page in the reference string, the program checks if that page is already present in the temporary array. If it is, there is no occurrence of a page fault, and the program proceeds to the next page. Conversely, if the page is not found in the temporary array, the program replaces the page that has been resident in the memory for the longest time with the new page. Additionally, the program keeps track of a head pointer that indicates the oldest page in the temporary array. When the head pointer reaches the end of the array, it wraps around to the beginning. The program generates an output comprising each page request, the contents of the frames, and whether a page fault occurred or not. This information is written to a text file named "FIFO.txt".

* **The second algorithm implemented is the _Optimal rule_.** In this algorithm, the page that will not be needed for the longest time in the future is replaced. The program creates an array of size equal to the reference string and initializes it with 0. For each page in the reference string, the program checks if the page is already present in the array. If it is, there is no page fault, and the program moves on to the next page. If it is not, the program searches the array to find the page that will not be needed for the longest time in the future. If such a page is found, it is replaced with the new page. If not, the page that was requested the longest time ago is replaced. The program outputs each page request and the contents of the frames, indicating whether there was a page fault or not, and writes this information to a text file named "Optimal.txt".

* **The third algorithm implemented is the _LFU rule_.** In this algorithm, the page that has been used the least number of times is replaced. The program creates a temporary array of size equal to the number of frames and initializes it with 0. For each page in the reference string, the program checks if the page is already present in the temporary array. If it is, the program increments a counter associated with the page. If it is not, the program replaces the page that has been used the least number of times with the new page. If multiple pages have been used the same number of times, the program replaces the one that has been in the memory for the longest time. The program outputs each page request and the contents of the frames, indicating whether there was a page fault or not, and writes this information to a text file named "LFU.txt".

### CONCLUSION:

In conclusion, this project implements three different page replacement algorithms:
*   First-In-First-Out (FIFO)
*   Optimal (OPT and MIN)
*   Least Frequently Used (LFU)

The program takes input from a text file containing a sequence of page requests, and simulates the behavior of each algorithm by keeping track of which pages are currently in memory and which ones have been evicted.

Based on the experimental results, it can be concluded that the Optimal algorithm provides the best overall performance in terms of minimizing page faults, followed by LFU and then FIFO. However, the choice of which algorithm to use may depend on the specific characteristics of the system being simulated. For example, if memory is very limited, the LFU algorithm may be more effective because it prioritizes evicting pages that are used infrequently.

Overall, this project demonstrates the importance of page replacement algorithms in managing memory and optimizing system performance. By understanding the trade-offs between these different algorithms and their specific use cases, system administrators and developers can make informed decisions about how to design and to optimize their systems to maximize efficiency.

