# EXP-12 -Implementation of Huffman Coding

## Aim:
To implement Huffman coding to compress the data using Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Assign the input string.

### Step 2:
Create the required tree nodes.

### Step 3:
Create a function to implement the huffman coding.

### Step 4:
Calculate frequency of occurence.

### Step 5:
Print the characters and its Huffman code.

## Program:
```
Developed by : Pooja A
Registration Number : 212222240072
```

## Get the input String:
```python
string=input("Pooja A 212222240072")
class NodeTree(object):
  def __init__(self,left=None,right=None):
    self.left=left
    self.right=right
  def children(self):
    return(self.left,self.right)
```    
    
## Create tree nodes:
```python
def huffman_code_tree(node, left=True, binString=''):
    if type(node) is str:
        return {node: binString}
    (l, r) = node.children()
    d = dict()
    d.update(huffman_code_tree(l, True, binString + '0'))
    d.update(huffman_code_tree(r, False, binString + '1'))
    return d
```

## Main function to implement huffman coding:
```python
freq={}
for c in string:
  if c in freq:
    freq[c]+=1
  else:
    freq[c]=1
freq=sorted(freq.items(),key = lambda x: x[1],reverse=True)
Nodes=freq
```

## Calculate frequency of occurrence:
```python
while len(Nodes) >1:
  (key1,c1) =Nodes[-1]
  (key2,c2) =Nodes[-2]
  Nodes=Nodes[:-2]
  Node=NodeTree(key1,key2)
  Nodes.append((Node,c1+c2))
  Nodes=sorted(Nodes,key=lambda x: x[1],reverse=True)
```

## Print the characters and its huffmancode:
```python
huffmanCode = huffman_code_tree(nodes[0][0])
print(' Char | Huffman code ')
print('----------------------')
for (char, frequency) in freq:
    print(' %-4r |%12s' % (char, huffmanCode[char]))
```

## Output:
![exp 12 out](https://github.com/poojaanbu0/HUFFMAN-CODING-/assets/119390329/83028481-1cc8-4ac8-8b85-f5c78bd6b424)

## Result:
Thus, the huffman coding was implemented to compress the data using python programming.
