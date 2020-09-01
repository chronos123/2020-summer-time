## 二叉树前序遍历创建
向左创建，每创建一个新的节点，判断新的左右然后再返回到递归
```py
class TreeNode:
    def __init__(self):
        self.val = ''
        self.left = None
        self.right = None

    def create(self):
        judge = input('是否继续输入数据, y/n: ')
        if judge.upper() == 'N':
            return None

        new_node = TreeNode()
        new_node.val = int(input('give the value: '))

        new_node.left = self.create()
        new_node.right = self.create()
        return new_node

    def output(self, root):
        if root:
            print(root.val, end=' ')
            self.output(root.left)
            self.output(root.right)


root1 = TreeNode()

root2 = root1.create()
root2.output(root2)
```
