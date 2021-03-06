状态模式总结
=====

状态模式和策略模式比较类似，都是利用多态把一些操作分配到一组相关的简单的类中。

在状态模式中，状态的变迁是由对象的内部条件决定，外界只需关心其接口，
不必关心其状态对象的创建和转化；而策略模式里，采取何种策略由外部条件决定。

而状态模式不同，对一个状态特别重要的对象，通过状态机来建模一个对象的状态；   
状态模式处理的核心问题是状态的迁移，因为在对象存在很多状态情况下，对各个business flow，各个状态之间跳转和迁移过程都是及其复杂的。   
例如一个工作流，审批一个文件，存在新建、提交、已修改、HR部门审批中、老板审批中、HR审批失败、老板审批失败等状态，涉及多个角色交互，涉及很多事件，这种情况下用状态模式(状态机)来建模更加合适；    
把各个状态和相应的实现步骤封装成一组简单的继承自一个接口或抽象类的类，通过另外的一个Context来操作他们之间的自动状态变换，通过event来自动实现各个状态之间的跳转。   
在整个生命周期中存在一个状态的迁移曲线，这个迁移曲线对客户是透明的。