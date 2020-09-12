# Python Tips

## I/O File

1. 创建文件并清空

   ```python
   f = open('Optres.txt','w+').close()
   ```

   Note: 即使文件已经存在，只要文件不在打开状态，这条语句依然可以清空文件内容

2. 输出字符串到 TXT 文件

   ```python
   a0 = np.ones(n)   # This is a vector (n,)
   for k in range (itermax):
       f.write('\n\n %s -th iteration\n' %k) # % 标记转换字符的开始
       np.savetxt(f,[a0],fmt='%.9f') # row-wise print [a0]  
   ```

   Note:

   1. [常用字符串格式化转换类型](https://docs.python.org/3.4/library/string.html)

      | [d,i] | 含义                                                         |
      | ----- | ------------------------------------------------------------ |
      | [d,i] | Decimal Integer. Outputs the number in base 10.              |
      | [e]   | Exponent notation. Prints the number in scientific           |
      | [f]   | Fixed point. Displays the number as a fixed-point number.  The default precision is 6. |
      | [s]   | 字符串 （使用str转换任意Python对象|

   2. 字符串有两个的话，需要用括号

      ```python
      flag = {'Location': 'internal', 'Quality': 'good', 'size': 'small'}
      tau = 1.5
      f.write('%s tau %s\n' % (flag,tau)) 
      ```

3. 自定义函数

   ```python
   def nptxt(file,comment,array):
        f.write('%-*s' %(20,comment))   #输出字符串 宽度 20 左对齐
        np.savetxt(f,array,fmt='%.9f')  #输出数组 精度 9
   ```

## Cprofile

[`cProfile`](http://doc.codingdict.com/python_352/library/profile.html)建议大多数用户；它是一个C扩展，具有合理的开销，使其适合于分析长期运行的程序

1. All analysis

   ```python
   python -m cProfile -o profile_output test1.py
   import pstats
   p = pstats.Stats('profile_output')
   p.sort_stats('cumulative').print_stats(20)
   ```

2. block analysis

   ```python
   import cProfile
   cp = cProfile.Profile()
   cp.enable()
   and
   cp.disable()
   cp.print_stats()
   ```

## Multiprocessing

### Using a pool of workers

The [Pool](https://docs.python.org/3/library/multiprocessing.html#multiprocessing.pool.Pool) class represents a pool of worker processes. It has methods which allows tasks to be offloaded to the worker processes in a few different ways.

For example:

```python
from multiprocessing import Pool, TimeoutError
import time
import os

def f(x):
    return x*x

if __name__ == '__main__':
    # start 4 worker processes
    with Pool(processes=4) as pool:

        # print "[0, 1, 4,..., 81]"
        print(pool.map(f, range(10)))

        # evaluate "f(20)" asynchronously
        res = pool.apply_async(f, (20,))      # runs in *only* one process
        print(res.get(timeout=1))             # prints "400"
```

### apply_async

>  apply_async(func[, args[, kwds[, callback[, error_callback]]]])
>
> *class* `multiprocessing.pool.` `AsyncResult`
>
> ​	The class of the result returned by `Pool.apply_async()` and `Pool.map_async()`.
>
> ​	 `get([timeout])`
>
> ​	Return the result when it arrives. If timeout is not `None` and the result does not arrive within `timeout` seconds then `multiprocessing.TimeoutError` is raised. If the remote call raised an exception then that exception will be reraised by get().

### [starmap](https://docs.python.org/3/library/multiprocessing.html#multiprocessing.pool.Pool.starmap)

> starmap(func, iterable[, chunksize]
>
> ​	Like [`map()`](https://docs.python.org/3/library/functions.html#map) except that the elements of the *iterable* are expected to be iterables that are unpacked as arguments.
>
> Hence an *iterable* of `[(1,2), (3, 4)]` results in `[func(1,2), func(3,4)]`
>
> ```python
> res = np.asarray(pool.starmap(Probname,zip([n for i in range (totaln)], \
>                                   [m for i in range (totaln)], \
>                                   x_ucurr)))
> ```


## Python tricks

### 产生连续编号的字符串

```python
import numpy as np
ls= ''
for i in range (68):
    ls=ls+( 'g'+ str(i+1)+'.f'.ljust(3))   # ljust(3) 补充成3个字符,即添加一个空格
```

##  Iterator & Generator

### [Generator](http://www.runoob.com/python3/python3-iterator-generator.html)

在 Python 中，使用了 yield 的函数被称为生成器（generator）。

跟普通函数不同的是，生成器是一个返回迭代器的函数，只能用于迭代操作，更简单点理解生成器就是一个迭代器。 

在调用生成器运行的过程中，每次遇到 yield 时函数会暂停并保存当前所有的运行信息，返回 yield 的值, 并在下一次执行 next() 方法时从当前位置继续运行。

调用一个生成器函数，返回的是一个迭代器对象。

```python
t =[1,2,3,4]
It = iter(t)     # Create iterator
next(It)
>>> 1
next(It)
>>> 2

G = (n  for n in range (4))    # Create Generator
next(G)
>>> 0

```

## Install pygmo

### Dependancies

1. Boost

```shell
   sudo apt-get install libboost-all-dev
```

## Matplotlib

### Fig size

1.0 text width

11pt latex: 5.1191 inches

12pt latex: 5.3975 inches

0.8 text width: 

```python
fig, ax = plt.subplots(1, 1, figsize=(4, 4))
```

0.5 text width

```python
fig, ax = plt.subplots(1, 1, figsize=(2.38, 2.38))
```

### Use latex text

```python
mpl.rcParams['text.usetex'] = True
mpl.rc('font', **{'family': "sans-serif"})
params = {'text.latex.preamble': [r'\usepackage{amsmath}']}
plt.rcParams.update(params)
```

### Marker size

```python
'$\u25A1$' -- h square
'$\u25EF$' -- h circle
```