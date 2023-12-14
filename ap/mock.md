## Mock Exam

----

### 2019 Mock Exam

#### Question 1 True or False

Please circle T if the following statement is true and F if the statement is false.


Q1. The value of `List.fold (+) -1 [1;2;3;4]` is `9`.

A1: **Ture**

Exp1: 

Step1: `List.fold (+) -1 [1;2;3;4]`

Step2: `List.fold (+) 0 [2;3;4]`

Step3: `List.fold (+) 2 [3;4]`

Step4: `List.fold (+) 5 [4]`

Step5: `List.fold (+) 9 []`

Step6: `9`

"List.fold" 作用是將一個函數套用到一個 list 的所有元素上，並且將結果累加起來，而 -1 是初始值，所以最後的結果是 9。

----

Q2. Evaluating the expression `([1;2] :> System.Object) :?> string list` will succeed.

A2: **False**

Exp2: 

`([1;2] :> System.Object)`会将 [1;2] 转换成 System.Object，而 `:?>` 是一个转换运算子，所以 `([1;2] :> System.Object) :?> string list` 会将 System.Object 转换成 string list，但是 System.Object 并不是 string list，所以转换失败。

----

Q3. For abitrary n, accessing the last element of `[|1 ..  n|]` will take constant time (as a function of n).

A3: **False**

Exp3: 

`[|1 ..  n|]` 是一个数组，而数组的最后一个元素的索引是 n - 1，所以访问最后一个元素的时间是 O(n)。

----

Q4. Evaluting the expression `fst (lazy (1,2))` will fail because of type mismatch.

A4: **True**

Exp4:

F#中的lazy用于创建一个惰性求值的值。lazy (1,2)创建一个惰性值的元组(1,2)。这个惰性值的类型是 `Lazy<int*int>`

fst函数用于获取元组的第一个元素，但它期望一个元组作为它的输入，而不是一个惰性值。由于`lazy (1,2)`不是一个元组，而是一个惰性值，所以直接传递给fst会导致类型不匹配。在这种情况下使用fst的正确方法是首先使用.Value强制求值惰性值，然后应用fst，如下所示:`fst (lazy (1,2)).Value`,这将返回1。

----

Q5. Taking the head of an empty list will fail at run time

A5: **True**

Exp5:

`List.head`函数用于获取列表的第一个元素，但它期望一个非空列表作为它的输入。如果传递一个空列表，它将引发一个异常。例如，`List.head []`将引发异常`System.ArgumentException`

----

Q6. Evaluting the expression `let x = printfn "hello"; 2` will print hello to the screen

A6: **True**

Exp6:

`printfn "hello"`是一个函数调用，它打印"hello"，然后打印一个换行符到屏幕上。分号(;)将这个表达式与下一个表达式2分开。let x =部分将整个表达式的结果分配给x。由于打印是序列中第一个表达式的一部分，所以当这段代码运行时，"hello"将被打印到屏幕上。值2是表达式序列的最终值，(x的值是2)，但它不影响打印操作。

----

Q7. The type of `[(1,2,3)]` is `(int * int * int) list`.

A7: **True**

Exp7:

`[(1,2,3)]`是一个包含一个元组的列表。元组是一个有序的值序列，它的类型是`(int * int * int)`。列表是一个有序的值序列，它的类型是`'a list`。由于元组是一个值，所以它可以作为列表的元素。因此，`[(1,2,3)]`是一个包含一个元组的列表，元组的类型是`(int * int * int)`，所以`[(1,2,3)]`的类型是`(int * int * int) list`。

----

Q8. The type of `Some (Some 42)` is `int option`.

A8: **False**

Exp8:

F#中的`Some(Some 42)`表示一个嵌套的option类型。内部的`Some 42`是`int option`类型，表示它是一个可选的整数。当它被包装在另一个Some中时，它变成了`option<option<int>>`，通常写成`int option option`。这表示一个可选值，其中值本身也是可选的。

----

Q9. Evaluating the expression `Option.bind Some None` returns `Some None`.

A9: **False**

Exp9:

在F#中，Option.bind接受一个函数和一个选项，并将该函数应用于选项中的值(如果存在)。在这种情况下，函数是Some，选项是None。

当Option.bind应用于Some和None时，它不会应用Some函数，因为None表示没有值。因此，这个表达式的结果是None，而不是Some None。

注意：由于 None 本身没有具体的类型信息，所以编译器不能确定 Option.bind Some None 表达式的确切类型。这就是为什么编译器给出了一个类型推断的错误。

----

Q10. The expression `let rec t = seq {yield 1; yield! t}` generates an inﬁnite sequence of increasing integers

A10: **False**

Exp10:

这个F#表达式定义了一个递归无限序列，但它并没有生成一个递增的整数序列。相反，它生成一个无限序列，其中每个元素都是1。序列从1开始(yield 1)，然后通过递归地再次生成整个序列t(yield! t)来继续。序列t本身以1开始，等等，无限期地。

结果是一个无限序列的1，而不是一个递增的整数序列。

----

Q11. The expression `List.map (fun n -> n + 2) [1,3,5,7]` returns `[3,3,5,7]`

A11: **False**

Exp11:

表达式`List.map (fun n -> n + 2) [1,3,5,7]`将一个函数应用于列表[1,3,5,7]中的每个元素。这个函数取每个元素n并返回n + 2。

列表的正确表示方式是使用分号 (;) 分隔元素，而不是逗号。所以，[1,3,5,7] 实际上是不正确的 F# 列表表示方式，它应该是 [1;3;5;7]。因此，结果应该是 [3;5;7;9]。

----

Q12.

The type deﬁnition
```fsharp
type Tree =
| Leaf of int
| Node of Tree * Tree 
```
deﬁnes leaf labelled trees

A12: **True**

Exp12:

`Tree`是一个带有两个case的discriminated union(标记联合)：

`Leaf of int`：这表示一个包含整数的叶子节点。这意味着这个树中的叶子是用整数标记的。

`Node of Tree * Tree`：这表示一个具有两个子节点的二叉树节点，每个子节点都是一个Tree。这可以是另一个Node或一个Leaf。

由于树的唯一标记部分是Leaf，它包含一个int，所以这是一个带有标记的树。Node本身除了它的子节点之外没有任何额外的标签或数据。因此，该语句为真。

----

#### Question 2 Trees

Expressions made of only strings and concatenation can be represented using the following tree data structure:

```fsharp
type STree =
| Val of string
| Concat of STree * STree
```

----

Q1. Define an element of the `STree` type that corresponds to the informal representation `("a" @ "b") @ ("c" @ "d")`.

