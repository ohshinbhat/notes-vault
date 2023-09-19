Binary tree has 0 to 2 sub branches
Root- top of the tree
Children- children of the top node
Leaf node- node which has no children
Sub-tree- part of the top node
Ancestors- traversing from leaf, parent node

Types:
1. Full binary tree -every node has either 0 or 2 children
2. Complete Binary tree- all levels have 2 children except the last level 
3. Perfect binary tree- all leaf nodes are in the same level
4. Balanced binary tree- height should be max log base 2 n
5. Degenerate tree- straight line, every node has 1 child

left ref | data | right ref
null if no child

`` class Node {
`` int data;
`` Node left;
`` Node right;
`` public Node (key){
``  data=key;
`` }
``}

Traversal:

Depth-first search-
In-order Traversal: Left-Root-Right
Pre-order Traversal: Root-Left-Right (Stack)
Post-Order Traversal: Left-Right-Root
Level-Order Traversal: top-down levels (Queue/Array) check left and right at each level

![[Pasted image 20230918054638.png]]
In-order: 4 2 5 1 6 3 7
Pre-order: 1 2 4 5 3 6 7
Post-order: 4 5 2 6 7 3 1

![[Pasted image 20230918054946.png]]
In-order: 4 2 8 5 1 6 3 9 7 10
Pre-order: 1 2 4 5 8 3 6 7 9 10
Post-order: 4 8 5 2 6 9 10 7 3 1


Breadth First Search-
Level Order Traversal: Level 1 2 3 ...
`class Solution {
`	public List<Integer> levelOrder(TreeNode root) { 
	`Queue<TreeNode> queue = new LinkedList<TreeNode>();
	`List<Integer> wrapList = new List<Integer>();
	`if(root == null) return wrapList;
	`queue.offer(root);
	`while(!queue.isEmpty()){
	` if(queue.peek().left != null) 
	`	 queue.offer(queue.peek().left);
	 `if(queue.peek().right != null) 
		` queue.offer(queue.peek().right);
		 `wrapList.add(queue.poll().val); 
	``} 
	`return wrapList; 
 ``}
``}

Pre-order Traversal with Stack:
`static ArrayList < Integer > preOrderTrav(Node curr) {
 `ArrayList < Integer > preOrder = new ArrayList < Integer > ();
 `if (curr == null) return preOrder;
 `Stack < Node > s = new Stack < > ();
 `s.push(curr);
 `while (!s.isEmpty()) {
 `` Node topNode = s.peek();
  `preOrder.add(topNode.data);
  `s.pop();
  `if (topNode.right != null)
   `s.push(topNode.right);
  `if (topNode.left != null)
  `` s.push(topNode.left);
 ``}
 `return preOrder;
``}

In-order Traversal with stack:
`static ArrayList < Integer > inOrderTrav(Node curr) {
 `ArrayList < Integer > inOrder = new ArrayList < > ();
 `Stack < Node > s = new Stack < > (); 
 `while (true) {
  `if (curr != null) {
  `` s.push(curr);
  `` curr = curr.left;
 ``} else {
  `if (s.isEmpty()) break;
  `` curr = s.peek();
   `inOrder.add(curr.data);
   `s.pop();
   `curr = curr.right;
   ``}
 ``} 
 `return inOrder;
``}


Pre-in-post order in one code:
import java.util.*;
class TreeNode {
 int val;
 TreeNode left; 
 TreeNode right; 
 TreeNode() {
 } 
 TreeNode(int val) {
  this.val = val; 
  } 
  } 
class Pair {
 TreeNode node;
 int num;
 Pair(TreeNode _node, int _num) { 
  num = _num;
  node = _node; 
  }
} 
public class trav {
 public static void allTraversal(TreeNode root, List < Integer > pre, List < Integer > in , List < Integer > post) {
  Stack < Pair > st = new Stack < Pair > (); st.push(new Pair(root, 1)); 
  if (root == null) return; 
  while (!st.isEmpty()) {
   Pair it = st.pop();
    // this is part of pre // increment 1 to 2 // push the left side of the tree 
    if (it.num == 1) {
     pre.add(it.node.val);
     it.num++; 
     st.push(it); 
     if (it.node.left != null) { 
      st.push(new Pair(it.node.left, 1));
    } 
 } 
// this is a part of in // increment 2 to 3 // push right 
 else if (it.num == 2) {
  in .add(it.node.val); 
  it.num++; 
  st.push(it); 
  if (it.node.right != null) { 
   st.push(new Pair(it.node.right, 1));
 } 
} // don't push it back again else 
{
post.add(it.node.val);
} 
} 
}