---
title: 前端
icon: circle-info
---

功能详情...


# 前端

## TypeScript

### 工具类型

#### Omit

Omit<Type, Keys>

> Released:
> [3.5](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-5.html#the-omit-helper-type)	

Constructs a type by picking all properties from `Type` and then removing `Keys` (string literal or union of string literals). The opposite of [`Pick`](https://www.typescriptlang.org/docs/handbook/utility-types.html#picktype-keys).

用于构造一个类型，忽略Type中的keys属性

### 类型断言

#### AS

类型断言，手动指定一个值的类型

```typescript
值 as 类型  
```

或

```typescript
<类型>值
```

**将一个联合类型断言为其中一个类型。**

**将一个父类断言为更加具体的子类。**

**将任何一个类型断言为 `any`**。

**将 `any` 断言为一个具体的类型。**

**as 可以将父类赋给子类，也可以把子类赋给父类，父类兼容子类时，它们可以相互进行类型断言**。

##### 双重断言

可以将任何类型断言为any再将其断言为另一个不兼容的类型，比如`as any as type`通常来说,这是错误的做法。（兼容：A是B的子集，B兼容A）。

> 类型断言只会影响 TypeScript 编译时的类型，类型断言语句在编译结果中会被删除。
>
> 类型断言不是类型转换，它不会真的影响到变量的类型。
>
> 若要进行类型转换，需要直接调用类型转换的方法。

#### extends

用来扩展类型，子类型继承父类型

### 类型

#### 空类型

##### void

空类型，与any相反。限制函数返回这为空时，函数可以直接return，不能return其他的结果。

把变量设置为void，这个变量只能接受undefined或null了。

##### never

代表**永远不**。button type，不兼容其他类型，只能赋值给另一个never。

用法：

函数返回类型为never时代表该函数永不返回，抛出异常的方法返回值就是never。

用来处理`switch case`或者`if else`所有的未处理类型 。

防止意外的 API 使用。

部分禁止结构类型。

限制函数参数。

### 声明文件

声明文件,d.ts作为后缀,为了获得代码补全和类型检查而使用。声明文件只包含类型不包含实现。第三方库通常自带声明文件，若没有，可以自己写。

```typescript
声明全局或局部变量：

declare var/let/const 声明变量/常量
declare function 声明函数
declare class 声明 class
declare enum 声明枚举变量
declare namespace 声明命名空间(空间下必须有属性才生效)
声明全局或局部类型：

interface 声明接口
type 声明类型别名
变量或类型的导入导出：

export 导出变量
export namespace 导出（含有子属性的）对象
export default ES6 默认导出
export = commonjs 导出模块
export as namespace UMD 库声明全局变量
扩展变量或模块：

declare global 在模块中声明全局变量或全局类型
declare module 声明模块或扩展模块
/// <reference /> 三斜线指令引用声明文件
#声明各种变量
```

一个声明文件中没有顶层的export或者import的时候，认为该文件是一个全局声明文件，在该文件内声明的变量或类型都是全局的，不需要import就可以在任何地方直接使用。

如果有export或import，则认为该文件是一个模块，要使用文件内声明的变量和类型，需要import对应的模块后再使用。

#### declare global

使用 `declare global` 可以在 npm 包或者 UMD 库的声明文件中扩展全局变量的类型。

`declare global` 块中的声明就是全局的。

`declare global` 块必须出现在模块声明文件中，才能有效声明全局变量或全局类型，也就是说在没有export或者import的情况下需要加上`export{}`才能生效。



## Vue

## CSS

## 项目结构