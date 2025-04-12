# Max & Min element in a Binary Tree

### [Link of the problem](https://www.geeksforgeeks.org/problems/max-and-min-element-in-binary-tree/1?itm_source=geeksforgeeks&itm_medium=article&itm_campaign=practice_card)

---

## Solution  : Recursive 
        for finding maximum element ->
        5 -> maximum = max(5 , max(maxBT(5->left) + maxBT(5->right))) --> this is calculated at every step
       / \
      3   4
     / \   \
    1   2   6 -> maximum = max(6, INT_MIN), it will return maximum = 6 to node 4
           / \
        NULL NULL -> if (root == NULL) return INT_MIN;
        
        for finding minimum element->
        5 -> minimum = min(5 , min(minBT(5->left) + minBT(5->right))) --> this is calculated at every step
       / \
      3   4
     / \   \
    1   2   6 -> minimum = max(6, INT_MAX), it will return minimum = 6 to node 4
           / \
        NULL NULL -> if (root == NULL) return INT_MAX;

Code:  
```cpp
class Solution
{
public:
    int findMax(Node *root)
    {
        if(!root) return INT_MIN;
        int maximum = max(root->data, max(findMax(root->left), findMax(root->right)));
        return maximum;
    }
    int findMin(Node *root)
    {
        if(!root) return INT_MAX;
        int minimum = min(root->data, min(findMin(root->left), findMin(root->right)));
        return minimum;
    }
};
