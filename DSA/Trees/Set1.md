# DSA Trees - Set 1

📋 Topics Included: 3

1. Inorder Traversal of a Binary Tree
2. Preorder Traversal of a Binary Tree
3. Postorder Traversal of a Binary Tree

---

# 1. Inorder Traversal of a Binary Tree

## Description

Given the root of a binary tree, perform an inorder traversal of the tree.

**Inorder Traversal:** Left → Root → Right

Example Tree:

```text
        1
       / \
      2   3
     / \
    4   5
```

Inorder Traversal:

```text
4 2 5 1 3
```

## C++ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

struct TreeNode {
    int data;
    TreeNode* left;
    TreeNode* right;

    TreeNode(int val) {
        data = val;
        left = nullptr;
        right = nullptr;
    }
};

void inorder(TreeNode* root) {
    if (root == nullptr)
        return;

    inorder(root->left);
    cout << root->data << " ";
    inorder(root->right);
}

int main() {
    TreeNode* root = new TreeNode(1);

    root->left = new TreeNode(2);
    root->right = new TreeNode(3);

    root->left->left = new TreeNode(4);
    root->left->right = new TreeNode(5);

    inorder(root);

    return 0;
}
```

### Time Complexity

O(N)

### Space Complexity

O(H)

---

# 2. Preorder Traversal of a Binary Tree

## Description

Given the root of a binary tree, perform a preorder traversal of the tree.

**Preorder Traversal:** Root → Left → Right

Example Tree:

```text
        1
       / \
      2   3
     / \
    4   5
```

Preorder Traversal:

```text
1 2 4 5 3
```

## C++ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

struct TreeNode {
    int data;
    TreeNode* left;
    TreeNode* right;

    TreeNode(int val) {
        data = val;
        left = nullptr;
        right = nullptr;
    }
};

void preorder(TreeNode* root) {
    if (root == nullptr)
        return;

    cout << root->data << " ";
    preorder(root->left);
    preorder(root->right);
}

int main() {
    TreeNode* root = new TreeNode(1);

    root->left = new TreeNode(2);
    root->right = new TreeNode(3);

    root->left->left = new TreeNode(4);
    root->left->right = new TreeNode(5);

    preorder(root);

    return 0;
}
```

### Time Complexity

O(N)

### Space Complexity

O(H)

---

# 3. Postorder Traversal of a Binary Tree

## Description

Given the root of a binary tree, perform a postorder traversal of the tree.

**Postorder Traversal:** Left → Right → Root

Example Tree:

```text
        1
       / \
      2   3
     / \
    4   5
```

Postorder Traversal:

```text
4 5 2 3 1
```

## C++ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

struct TreeNode {
    int data;
    TreeNode* left;
    TreeNode* right;

    TreeNode(int val) {
        data = val;
        left = nullptr;
        right = nullptr;
    }
};

void postorder(TreeNode* root) {
    if (root == nullptr)
        return;

    postorder(root->left);
    postorder(root->right);
    cout << root->data << " ";
}

int main() {
    TreeNode* root = new TreeNode(1);

    root->left = new TreeNode(2);
    root->right = new TreeNode(3);

    root->left->left = new TreeNode(4);
    root->left->right = new TreeNode(5);

    postorder(root);

    return 0;
}
```

### Time Complexity

O(N)

### Space Complexity

O(H)
