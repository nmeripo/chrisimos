#### Ordered Counter recipe
```python
class OrderedCounter(Counter, OrderedDict):
    pass
```
```python
OrderedCounter.__mro__

(<class '__main__.OrderedCounter'>, <class 'collections.Counter'>, <class 'collections.OrderedDict'>, <class 'dict'>, <class 'object'>)
```
