# Fortran to Python (F2PY)
1. Set up [Ref](https://blog.finaltheory.me/research/Introduction-to-F2PY.html) 

   ```fortran
   subroutine func(nvar,ncon,x,f,g)   # fortran 主程序变成子程序
   !f2py intent(in) nvar              # in, out 为输入输出
   !f2py intent(in) ncon
   !f2py intent(in) x
   !f2py intent(out) g
   !f2py intent(out) f
   !f2py depend(nvar) x				# depend 表示 x [nvar] 数组
   !f2py depend(ncon) g
   ```

   

2. F2py Command
```python
f2py -c -m test test.f90			
```

