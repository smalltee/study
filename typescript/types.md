# 1.Typescript创建自定义类型
1. 定义类型使用 Type声明
2. 定义接口使用 interface

### 使用Type和interface定义的类型有什么不同与相同点
1. 相同点： 都可以定义对象类型，都可以继承其他类型
2. 不同点： Type可以定义的范围更广，交叉定义，映射定义

### 泛型类型
1. 通过参数的方式告知数据类型的名字，后续都可以使用该名字作为类型来声明
2. 泛型的本意是定义的时候其实我也不是很清楚是什么类型，里面的数据结构是什么样的。只知道后面使用的时候定义了该类型的数据或对象，其结构都是要保持一致，从最外层做了一次约束限制
3. 与any的区别：any也可以达到上面两点的目的，但做不到约束限制作用


#### 泛型类型
1. 通过尖括号来定义泛型类型的名称，后续使用的使用都用定义的这个名称作为预期的类型来约束

`
官网示例 function identity<Type>(arg: Type): Type {
  return arg;
}`

`也可以写成function identity<TypeA>(arg: TypeA): TypeA {
  return arg;
}`

2. 泛型数组与普通类型数组使用方式一样

`function identity<TypeA>(arg: TypeA[]): TypeA[] {
  return arg;
}`

### 泛型函数

1. 定义泛型函数：还是通过尖括号来定义泛型函数的名称，参数与预期的函数保持一致，在函数体中来赋值泛型变量对应的实际函数

`function identity<TypeA>(arg: TypeA): TypeA {
  return arg;
}
`

`let myIdentity: <Input>(arg:Input)=>Input=identity
`

`参数不匹配就会报错 let myIdentity: <Input>(arg:Input, arg1:Input)=>Input=identity
`

### 泛型类
1. 通过尖括号中的名字来定义泛型类型，并在类定义中使用该类型名称来完成约束限制

`class GenericNumber<NumType> {
  zeroValue: NumType;
  add: (x: NumType, y: NumType) => NumType;
}
`

`let myGenericNumber = new GenericNumber<number>();`
`myGenericNumber.zeroValue = 0;`
`myGenericNumber.add = function (x, y) {
  return x + y;
};`


# 2.Keyof


# 3.Typeof