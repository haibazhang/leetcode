# 设计原则

敏捷开发强调SOLID五大原则。

## 职责单一原则（Single Responsibility Principle）

一个类/模块只负责一个职责/功能。

这条原则的目的是让类尽可能的“高内聚，低耦合”。

内聚和耦合意思比较接近，分水岭就是是否与职责有关。

* 内聚是指把职责相关的逻辑放在一起，高内聚就是把职责相关的尽可能多；
* 耦合是指把职责无关的东西也放在一起，低耦合尽量把职责无关的逻辑尽可能少；

设计是随着业务演变的。 举个例子，比如Useinfo领域模型中，最初职责是比较单一的，但随着业务发展，地址相关逻辑迅速膨胀。 当这个类做的事情明显超过一件，则应该划分出新的Address类。

## 开闭原则（Open Closed Principle）

一个类应该对扩展开放，对修改封闭。

这条原则是架构设计的主导原则，目的是：让系统易于扩展。

同样，想要应用好开闭原则需要熟知业务，例如封装一个table组件—— 我们参考element-ui封装的[table组件](https://element.eleme.cn/#/zh-CN/component/table)。

vue组件会把数据样式等变化的部分抽象成_属性_，把容器类组件的子组件抽象成_插槽_，而组件生命周期输入动作等则抽象成_事件_。 在文档中我们看到，table暴露的属性包括表格数据、表格的行样式; table单元格默认是文字，但也可能是其它任意组件，应对这种变化（业务需求）就需要定义插槽（插槽还能支持父组件到子组件传递数据）。插槽其实就是接口（字面意义也是哦），你可以将任何具体组件放入插槽（提供接口的实现）。文档中可以看到table中的定义了默认插槽（单元格）以及头部插槽。 最后，用户对table的动作，比如点击单元格，可以作为一个事件传递到组件外部。

## 里式替换原则（Liskov Substitution Principle）

子类对象能够替换程序中父类对象出现的任何地方，并且保证原来程序的逻辑行为不变及正确性不被破坏。

这条原则的目的是：所有子类可以安全（无侵入）地替换父类。

可见里式替换原则是用来指导（约束）子类设计的。在实际操作中比较容易实现，即子类要遵守父类定下的“协议”：包括函数声明要实现的功能；对输入、输出以及异常的约定；

[source](https://github.com/haibazhang/lib/blob/master/src/cs/design-patterns/设计原则.md) \| [edit-online](https://github.com/haibazhang/lib/edit/master/src/cs/design-patterns/设计原则.md)
