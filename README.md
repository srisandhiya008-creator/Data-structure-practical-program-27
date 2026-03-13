# Node class for BST
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None


# Function to insert nodes in BST
def insert(root, key):
    if root is None:
        return Node(key)

    if key < root.data:
        root.left = insert(root.left, key)
    else:
        root.right = insert(root.right, key)

    return root


# Postorder traversal (Left -> Right -> Root)
def postorder(root):
    if root:
        postorder(root.left)
        postorder(root.right)
        print(root.data, end=" ")


# Main program
root = None

# Example values (like real-time input data)
values = [50, 30, 20, 40, 70, 60, 80]

# Insert values into BST
for v in values:
    root = insert(root, v)

print("Postorder Traversal of BST:")
postorder(root)# Data-structure-practical-program-27
