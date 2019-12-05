# Numba [Home](https://numba.pydata.org/numba-doc/dev/index.html)
​	Numba translates Python code into fast executing native code. In order to generate fast native code, many dynamic features of Python need to be translated into static equivalents. This includes dynamic typing as well as polymorphism. The approach taken in numba is using type inference to generate type information for the code, so that it is possible to translate into native code. If all the values in a numba compiled function can be translated into native types, the resulting code will be competitive with that generated with a low level language.

## [Supported Features](http://numba.pydata.org/numba-doc/dev/reference/numpysupported.html)
*  ```python
  # not support
  np.size() 
  ```

## [Types and Signature](https://numba.pydata.org/numba-doc/dev/reference/types.html#numba.typeof)
1. Multiple Heterogeneous Output (包含数组)
   ```python
   import numba
   from numba import jit,njit,vectorize,float64,int64,f8
   @jit(numba.types.Tuple((float64[:], float64[:,:]))(float64[:], float64[:,:]),nopython=True) # 使用 Tuple 返回
   def f(a, b) :
   	return a, b
   ```

2. Vectorization (定义标量间的运算,但是支持向量运算)

   ```python
   @vectorize([float64(float64, float64)])
   def xsampling(xl,xu):
       x = xl+(xu-xl)*np.random.random_sample()
       return x
   ```

3. Numba.typeof (Signature 也可以用这个命令表示)

   ```python
   numba.typeof(0.1)
   >>> float64
   numba.types.Tuple((float64[:], float64[:,:]))
   >>> (array(float64, 1d, A), array(float64, 2d, A))
   ```

## Inspect 

```python
foo.inspect_types(pretty=True)   #foo 是 JITTED FUNCTION
```

## [Frequently Asked Questions](https://numba.pydata.org/numba-doc/dev/user/faq.html)

> 1. Numba doesn’t seem to care when I modify a global variable. 
>    Numba considers global variables as compile-time constants. If you want your jitted function to update itself when you have modified a global variable’s value, one solution is to recompile it using the recompile() method. This is a relatively slow operation, though, so you may instead decide to rearchitect your code and turn the global variable into a function argument.

So.  Jitted Function 里面如果有动态变量的话,是一定会出错的. 因此,如果函数包含动态数组的话, 是无法使用 Nopython Mode 的.