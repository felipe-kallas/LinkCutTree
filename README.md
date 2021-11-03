# LinkCutTrees
C++ implementation of Link Cut Trees, made by Lucian Bicsi. It has been described on the following [blog](https://codeforces.com/blog/entry/75885).

It implements Link Cut Trees without the explicit distinction of parents and path-parents. This is done by storing only a general parent node of the current node. It implicitly distinguishes parents from path-parents through the following idea:
- If the current node has a parent node, and this parent node also has the current node as one of it's children, both nodes are a part of the same splay tree.
- If the current node has a parent node, and this parent node doesn't have the current node as one of it's children, these nodes are a part of separate splay trees, and the parent node is actually a path-parent on the Link Cut Tree.

It also adds the functionality of being able to calculate sums of subtrees on the given tree. This is done by recording the sum of information of "virtual subtrees", which refers to all the subtrees of a node, except for the one the in the Splay. This idea is explained with more detail on the following [blog](https://codeforces.com/blog/entry/67637).