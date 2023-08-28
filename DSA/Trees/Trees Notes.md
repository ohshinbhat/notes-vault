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

Traversal:
Depth-first search:
In-order Traversal: Left-Root-Right
Pre-order Traversal: Root-Left-Right (Stack)
Post-Order Traversal: Left-Right-Root
Level-Order Traversal: top-down levels (Queue/Array) check left and right at each level


Pre-order Traversal using stack and list:
`static ArrayList < Integer > preOrderTrav(Node curr) {
	`ArrayList < Integer > preOrder = new ArrayList < Integer > (); 
	`if (curr == null) return preOrder; 
	`Stack < Node > s = new Stack < > (); 
	`s.push(curr); 
	`while (!s.isEmpty()) { 
		`Node topNode = s.peek(); 
		`preOrder.add(topNode.data); 
		`s.pop(); 
		`if (topNode.right != null) 
			`s.push(topNode.right);
		`if (topNode.left != null) 
		``	s.push(topNode.left); 
	`` } 
	`return preOrder;`

