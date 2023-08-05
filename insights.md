# insights 

## homework

### hw01

> Let's try to write a function that does the same thing as an `if` statement.
> ```python
> def if_function(condition, true_result, false_result):
>     """Return true_result if condition is a true value, and
>     false_result otherwise.
>
>     >>> if_function(True, 2, 3)
>     2
>     >>> if_function(False, 2, 3)
>     3
>     >>> if_function(3==2, 3+2, 3-2)
>     1
>     >>> if_function(3>2, 3+2, 3-2)
>     5
>     """
>     if condition:
>         return true_result
>     else:
>         return false_result
> ```
> Despite the doctests above, this function actually does *not* do the same thing as an `if` statement  in all cases. To prove this fact, write functions `cond`, `true_func`, and `false_func` such that `with_if_statement` prints the number `47`, but `with_if_function` prints both `42` and `47`.
> ```python
> def with_if_statement():
>     """
>     >>> result = with_if_statement()
>     47
>     >>> print(result)
>     None
>    """
>     if cond():
>         return true_func()
>     else:
>         return false_func()
> ```
> ```python
> def with_if_function():
>     """
>     >>> result = with_if_function()
>     42
>     47
>     >>> print(result)
>     None
>     """
>     return if_function(cond(), true_func(), false_func())
> ```
> ```python
> def cond():
>     "*** YOUR CODE HERE ***"
> ```
> ```python
> def true_func():
>     "*** YOUR CODE HERE ***"
> ```
> ```python
> def false_func():
>     "*** YOUR CODE HERE ***"
> ```



解答：

cond函数应该是`return False`

true_func是`print(42)`

false_func是`print(47)`

因为调用`with_if_function`时，其实是调用`if_condition`, 而这个函数**在返回之前要评估他的每一个参数**，因此会把42, 47都打印出来。而`with_if_statement`则会先判断cond的条件，再选择其一进行打印。

不仅强调了函数调用的过程，还指明`print`是一个非常特殊的函数。