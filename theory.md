To generate an expression tree, given an expression, we first convert the expression to its postfix form. From the postfix expression, we read one symbol at a time from left to right. If the current symbol is an operand, then we push a tree of one node consisting of the operator onto a stack. If the symbol is an operator, then we pop two trees from the stack and create a tree with the root containing the operator and the result of the pop operations as the right and the left subtrees in that order. The resulting tree is again pushed onto the stack. When we have read all the symbols, the equivalent expression tree is the only element in the stack and a pop operation would give us the tree. The following example illustrates the algorithm. Let the postfix expression be a b + f - c d * e + /.

  - When we first read 'a' and 'b' in that order and create two trees containing a single node 'a' and 'b' respectively.  
  - These trees are then pushed on to the stack in that order.  
  - When we encounter the '+' operator, we pop two trees from the stack, creating a tree with '+' as the root and the two trees as the right and the left childs respectively.  
  - On reading the operand 'f', we create a tree with 'f' as a single node and push it on to the stack.  
  - On reading a '-' we create the tree with '-' as the root and the two previously created trees as its children and push the new tree onto the stack.  
  - Similarly, on reading 'c' and 'd', the stack has three trees; '-' and two new trees corresponding to nodes 'c' and 'd'.  
  - On reading a '*', the stack has two trees; '-' and a new tree consisting of '*' as the root and 'c' and 'd' as its children.  
  - Continuing further, we create the tree with '+' as the root. On reading the last '/', the final tree is created.  

