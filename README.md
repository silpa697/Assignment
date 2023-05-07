First we need to extract all the edge information (If not already given) in the form of the pair (u, v) where u = starting node and v = ending node. We should store all the edge information in an array.
Then we will iterate through the array selecting every pair and checking the following:
If the ultimate parent of u and v(checked using the findPar() method of the Disjoint set) becomes the same,  we should increase the count of extra-edges by 1.
Because the same ultimate parent means the nodes are already connected and so we can consider the current edge as an extra edge.
But if the ultimate parents are different, then we should apply the union(either unionBySize() or unionByRank()) method on those two nodes.
Thus we will get the count of the extra edges. Now it’s time to count the number of components. In order to do so, we will just count the number of the nodes that are the ultimate parent of themselves.
We will iterate over all the nodes and for each node, we will check the following:
If the node is the ultimate parent of itself, we will increase the count of components by 1.
Otherwise, we will continue to the next node.
This checking will be done using the parent array inside the Disjoint set.

Finally, we will check the count of extra edges and the number of components. If the count of extra-edges is greater or the same, we will return the answer that is (number of components – 1), and otherwise, we will return -1.



Time complexity:O(E)+O(N)  E = no. of edges and N = no. of nodes
Space Complexity:O(2N) where N = no. of nodes. 2N for the two arrays(parent and size) of size N we have used inside the disjoint set.
