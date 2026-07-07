**Generator（生成器）是一种特殊的 Iterator（迭代器）。**  
**所有 generator 都是 iterator，但不是所有 iterator 都是 generator。**

Iterator（迭代器）
│
├── list_iterator
├── tuple_iterator
├── dict_keyiterator
├── ...
└── Generator（生成器）

**Iterator 是一种对象，它可以一个一个地产生数据。**

它必须实现两个方法：

	- `__iter__()`
	- `__next__()`

Generator 是 **Python 自动帮你写好的 iterator。**

![[截屏2026-07-06 16.23.16.png]]

### yield from
```python
def countdown(k):
	if k > 0:
		yield k
		# yield countdown(k-1)这样是不行的！因为这就返回了一个generator而不是数值
		
		# for x in count down(k-1):
		# 	yield x
		# 以上可以写为
		yield from countdown(k-1)	
	else:
		yield 'Blast off'
		
		
			
			
```

![[截屏2026-07-06 18.31.06.png]]

---
# Example: partitions


![[截屏2026-07-06 18.38.53.png]]