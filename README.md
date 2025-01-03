# What is bigger-xml ?

#### A Python library designed for efficiently generating large XML files. BXML leverages a native C extension to store and process data, enabling it to manage substantial datasets and generate XMLs with improved performance.


## Some key benefits of using the bigger-xml library:

1. **Enhanced Performance with C Language:** Utilizes C programming to optimize the addition of new XML elements, attributes, and the overall process of generating and saving XML files.

2. **Efficient Memory Management:** Allocates memory using C, ensuring automatic release when there are no references to the XML data, reducing memory consumption.

3. **Handling Large Datasets:** Leverages C language to efficiently process and manage XML files with substantial data, ensuring better performance and scalability.

## Usage

#### 1. Import Library in python
```python
from bxml import *
```

#### 2. Initialize the root XML element.

```python
root = etree.Element("Root")

# Sample XML File

# <Root>
# </Root>
```

#### 3. Add a child element to the root element and assign a value to the XML tag.

```python
root = etree.Element("Root")
child1 = etree.SubElement(root, "Child1")
child1.text = 12.33
child2 = etree.SubElement(root,"Child2")
child2.text = 'bxml'

# Sample XML File

# <Root>
#   <Child1>12.33</Child1>
#   <Child2>bxml</Child2>
# </Root>
```

#### 4. Add an attribute to the XML element.

```python
root = etree.Element("Root")
child1 = etree.SubElement(root, "Child1")
child1.text = 12.33
child2 = etree.SubElement(root,"Child2")
child2.text = 'bxml'
child2.set("name","Krishna")

# Sample XML File

# <Root>
#   <Child1>12.33</Child1>
#   <Child2 name='Krishna'>bxml</Child2>
# </Root>
```

#### 5. Search for an XML element using its tag.


```python
root = etree.Element("Root")
child1 = etree.SubElement(root, "Child1")
child1.text = 12.33
child2 = etree.SubElement(root,"Child2")
child2.text = 'bxml'
child2.set("name","Krishna")

search = root.findAll('Child1')
search[0].text = 50

# Sample XML File

# <Root>
#   <Child1>50</Child1>
#   <Child2 name='Krishna'>bxml</Child2>
# </Root>
```

#### 6. Remove an element from the XML.

```python
root = etree.Element("Root")
child1 = etree.SubElement(root, "Child1")
child1.text = 12.33
child2 = etree.SubElement(root,"Child2")
child2.text = 'bxml'
child2.set("name","Krishna")

search = root.findAll('Child1')
search[0].text = 50

etree.remove(child1)

# Sample XML File

# <Root>
#   <Child2 name='Krishna'>bxml</Child2>
# </Root>
```

#### 7. Generate XML File.

```python
root.save("Test",True)

# The save function accepts three parameters, as described below:
# root.save(file_name,xmlDeclaration = True, encoding = 'ASCII')
#
#
# file_name: The name of the file to save the XML data.
# xmlDeclaration (optional): A boolean value to specify whether to include the XML declaration. Default is True.
# encoding (optional): The character encoding to use for the file. Default is 'ASCII'.
```