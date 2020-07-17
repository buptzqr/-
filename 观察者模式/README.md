# 观察者模式
## 动机
在软件构建过程中，我们需要为某些对象建立一种“通知依赖关系” ——一个对象（目标对象）的状态发生改变，所有的依赖对象（观察者对象）都将得到通知。如果这样的依赖关系过于紧密，将使软件不能很好地抵御变化。
## 模式定义
定义对象间的一种一对多（变化）的依赖关系，以便当一个对象(Subject)的状态发生改变时，所有依赖于它的对象都得到通知并自动更新。
## 要点总结
- 使用面向对象的抽象，Observer模式使得我们可以独立地改变目标与观察者，从而使二者之间的依赖关系达致松耦合。
- 目标发送通知时，无需指定观察者（不需要指定特定的观察者），通知（可以携带通知信息作为参数）会自动传播。
- 观察者自己决定是否需要订阅通知，目标对象对此一无所知。
- Observer模式是基于事件的UI框架中非常常用的设计模式，也是MVC模式的一个重要组成部分。
## 我的总结
- 应用场景是比如要写一个文件分割器，需要写一个进度条的功能，对于不同的平台，进度条有不同的实现方法，比如对于console可能就是...，对于windows可能就是常见的那种进度条。所以观察者模式的做法就是对实现不同的进度条的类，共同继承自一个抽象类（iprogress），实现相关方法，这个抽象类就是observer。
- 对应类图attach是addProgress，detach是removeProgress，notify是onProgress，在这里我们没有把这三个方法放到父类中。也就是subject和concreteSubject合二为一了。
- concretObserver相当于consoleNotifer和mainform。
## 类图
![image](https://github.com/buptzqr/CPP-Design-Patterns/blob/master/IMAGE/%E8%A7%82%E5%AF%9F%E8%80%85%E6%A8%A1%E5%BC%8F/%E7%B1%BB%E5%9B%BE.png)