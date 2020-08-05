#### Ordered Counter recipe
```python
class OrderedCounter(Counter, OrderedDict):
    pass
```
```python
OrderedCounter.__mro__

(<class '__main__.OrderedCounter'>, <class 'collections.Counter'>, <class 'collections.OrderedDict'>, <class 'dict'>, <class 'object'>)
```
#### Remove punctuation
```python
def strip_punct(text):
    table = str.maketrans(dict.fromkeys(string.punctuation))
    return text.translate(table) 
```

#### Flatten a 2D list
```python
def flatten_list(l):
    return [item for subl in l for item in subl]
```
