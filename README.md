[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=11973595&assignment_repo_type=AssignmentRepo)
# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

Add your answers to this markdown file.

1. Asymptotic analysis could be misleading compared to practice in a few different ways. Firstly, just because algorithm A is more efficient asymptotically than algorithm B, it doesn't mean that with the same input A will always be more efficient that algorithm B, just that it will tend to be at large numbers. This ties into a second confusing thing, where the average-case for algorithm A may be better than algorithm B, but the best case of B may be better than A. This is like the example of comparing insertion sort's best case of n to quick sort's best case of nlogn. Quick sort is a much more efficient algorithm, but when given a already sorted array, it will confirm it is sorted more quickly than quick sort. A third misleading aspect of asymptotic analysis is that just because two algorithms share the same asymptotic complexity of say nlogn, one is still likely faster than the other. This is because when considering the asymptotic complexity of an algorithm, we are essentially considering the magnitude of its variables. For example, 3nlogn would be more efficient than 100nlogn, but they are still part of the same $\Theta(nlogn)$.

2. Confirmed with a quick google search that a binary search tree's asymptotic complexity is $\Theta(logn)$ since it essentially divides the problem in half with each comparison.

I would expect the jump in size from 1,000 to 10,000 elements in an index wouldn't increase the time for the search by that much with a log based complexity. I'm not 100% sure on how to relate this through logs, but since this is a log base 2 and 1000 is near 1024, or 2^10, that is about half a second per doubling. Then, that is a little more than 3 doublings, so maybe add 1.75 seconds to the total. I would guess that it would take about 6.75 seconds to search a group of 10,000 elements with the binary search tree.

3. If I found that it actually took 100 seconds to search the tree, I would have to consider other factors. Maybe the first time I measured the time with 1000 elements, I got really lucky and found it almost immediately, then the second time I measured the time with 10,000 elements I got really unlucky and it was one of the last values checked. For a binary search tree, I would still be surprised if the difference were that great even with that disparity in the attempts. Secondly, I would have to consider perhaps something about the machine I was running it on was different. Could be different hardware specs, or on the same machine, just different background programs running. A third way this could happen is if maybe the implementation of the binary search tree had some built-in restriction in its use I wasn't aware of.