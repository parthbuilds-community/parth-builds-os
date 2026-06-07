# DSA Trees - Set 1

📋 Topics Included: 4

1. Inorder Traversal
2. Preorder Traversal
3. Postorder Traversal
4. Level Order Traversal

---

# 1. Inorder Traversal

### LeetCode Problem

🔗 https://leetcode.com/problems/binary-tree-inorder-traversal/

### Description

In Inorder Traversal, nodes are visited in the following order:

**Left → Root → Right**

Example:

```text
      1
     / \
    2   3
```

Inorder Traversal:

```text
2 1 3
```

### C++ Code

```cpp
class Solution {
public:
    void inorder(TreeNode* root, vector<int>& ans) {
        if (!root) return;

        inorder(root->left, ans);
        ans.push_back(root->val);
        inorder(root->right, ans);
    }

    vector<int> inorderTraversal(TreeNode* root) {
        vector<int> ans;
        inorder(root, ans);
        return ans;
    }
};
```

### Time Complexity

O(n)

### Space Complexity

O(h)

---

# 2. Preorder Traversal

### LeetCode Problem

🔗 https://leetcode.com/problems/binary-tree-preorder-traversal/

### Description

In Preorder Traversal, nodes are visited in the following order:

**Root → Left → Right**

Example:

```text
      1
     / \
    2   3
```

Preorder Traversal:

```text
1 2 3
```

### C++ Code

```cpp
class Solution {
public:
    void preorder(TreeNode* root, vector<int>& ans) {
        if (!root) return;

        ans.push_back(root->val);
        preorder(root->left, ans);
        preorder(root->right, ans);
    }

    vector<int> preorderTraversal(TreeNode* root) {
        vector<int> ans;
        preorder(root, ans);
        return ans;
    }
};
```

### Time Complexity

O(n)

### Space Complexity

O(h)

---

# 3. Postorder Traversal

### LeetCode Problem

🔗 https://leetcode.com/problems/binary-tree-postorder-traversal/

### Description

In Postorder Traversal, nodes are visited in the following order:

**Left → Right → Root**

Example:

```text
      1
     / \
    2   3
```

Postorder Traversal:

```text
2 3 1
```

### C++ Code

```cpp
class Solution {
public:
    void postorder(TreeNode* root, vector<int>& ans) {
        if (!root) return;

        postorder(root->left, ans);
        postorder(root->right, ans);
        ans.push_back(root->val);
    }

    vector<int> postorderTraversal(TreeNode* root) {
        vector<int> ans;
        postorder(root, ans);
        return ans;
    }
};
```

### Time Complexity

O(n)

### Space Complexity

O(h)

---

# 4. Level Order Traversal

### LeetCode Problem

🔗 https://leetcode.com/problems/binary-tree-level-order-traversal/

### Description

Level Order Traversal visits nodes level by level using a queue.

Example:

```text
      1
     / \
    2   3
```

Level Order Traversal:

```text
1
2 3
```

### C++ Code

```cpp
class Solution {
public:
    vector<vector<int>> levelOrder(TreeNode* root) {
        vector<vector<int>> ans;

        if (!root)
            return ans;

        queue<TreeNode*> q;
        q.push(root);

        while (!q.empty()) {
            int size = q.size();
            vector<int> level;

            for (int i = 0; i < size; i++) {
                TreeNode* node = q.front();
                q.pop();

                level.push_back(node->val);

                if (node->left)
                    q.push(node->left);

                if (node->right)
                    q.push(node->right);
            }

            ans.push_back(level);
        }

        return ans;
    }
};
```

### Time Complexity

O(n)

### Space Complexity

O(n)
