### How python execute codes
```python
class Base:
    def __init__(self):
        self.setup()

    def setup(self):
        print("Base setup")


class Child(Base):
    def setup(self):
        print("Child setup")
        
        
c = Child()
```
创建对象时：
c = Child()
python 做的事情是：
1. 创建一个Child类型的对象
2. 调用 Base.init(c)
	1. Child 没有定义__ init__， 所以会用Base.\_\_init__
3. 但type(c) == Child, 所以`self.setup()` 等价于`Child.setup(c)`



decorator
```python
def logger(func):
	def wrapper():
		print("Before running")
		result = func
		print("After running")
		return result
	return wrapper #一定要return！
	
	
@decorator
def my_function():
	print("Running function body...")
	return "Done!"
```

1. Define the function my_function()
2. When Python sees `@decorator`, it is equivalent to:
`my_function = decorator(my_function)`
所以说 如果不写
3. When calling my_function(), you’re actually executing wrapper()
4. Inside wrapper(), it first runs the pre-processing logic → calls the original function → then runs the post-processing logic.

**