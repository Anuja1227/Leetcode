# Sum of Binary Tree Problem

### [Link of the problem](https://www.geeksforgeeks.org/problems/sum-of-binary-tree/1?itm_source=geeksforgeeks&itm_medium=article&itm_campaign=practice_card)

---

## Solution  
Recursive Solution:

     5 -> sum = 5 + sumBT(5->left) + sumBT(5->right) --> this is calculated at every step  
    / \  
   3   4  
  / \   \  
 1  2    6 -> sum = 6 + 0 + 0, it will return sum = 6  
        / \  
    NULL  NULL  -> if (root == NULL) return 0;  


Code:  
```cpp
class Solution {
  public:
    int sumBT(Node* root) {
        if(!root) return 0;
        int sum = root->data + sumBT(root->left) + sumBT(root->right);
        return sum;
    }
};
