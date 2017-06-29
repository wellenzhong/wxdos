# 引用 {#引用}

WXML 提供两种文件引用方式`import`和`include`。

### import {#import}

`import`可以在该文件中使用目标文件定义的`template`，如：

在 item.wxml 中定义了一个叫`item`的`template`：

```
这里应该有代码
```

在 index.wxml 中引用了 item.wxml，就可以使用`item`模板：

```
这里应该有代码
```

### import 的作用域 {#import-的作用域}

import 有作用域的概念，即只会 import 目标文件中定义的 template，而不会 import 目标文件 import 的 template。

**如：C import B，B import A，在C中可以使用B定义的`template`，在B中可以使用A定义的`template`，但是C不能使用A定义的`template`**。

```
这里应该有代码
```

```
这里应该有代码
```

```
这里应该有代码
```

### include {#include}

`include`可以将目标文件除了`<template/>`的整个代码引入，相当于是拷贝到`include`位置，如：

```
这里应该有代码
```

```
这里应该有代码
```

```
这里应该有代码
```



