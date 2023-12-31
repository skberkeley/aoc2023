## Part 1
Algorithmically, Part 1 was fairly straightfoward: Simulate the act of stepping through the graph until the end node is reached. I stored the network being stepped through as a Map from NodeID's to the pairs of NodeID's that could be stepped to from that node. Of course, the code was written with the assumption that a finite solution existed, but one could certainly construct a situation in which the path given describes a cycle, preventing a solution.

## Part 2
As a first try, I tried writing a brute force solution where multiple nodes are tracked. Rather predictably, this resulted in the program not terminating. After looking at some comments on the subreddit, it seems like a possible solution involves using cycles and LCMs. 
As a second attempt, I'll try tracking whether each node tracked has reached a goal state, and assume (rather lazily) that each node will cycle back to a goal state after a fixed number of steps. As another lazy simplification, maybe the number of steps to reach any goal state from any start is the length of it's cycle. So all we need to do is find is the lcm of the number of steps each start takes to reach a goal node.
It worked! lol