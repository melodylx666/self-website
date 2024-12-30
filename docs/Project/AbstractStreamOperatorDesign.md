# 自定义StreamOperator

## 原理

StreamOperator接口提供了其生命周期的抽象方法，我们可以继承其抽象类AbstractStreamOperator，并覆盖其中的方法进行实现。

如果需要接受上游数据，就必须实现OneInputStreamOperator或者TwoInputStreamOperator接口，主要通过输入的数量来判断。

## 具体步骤：一个通用的定时，定量的输出算子的设计

1. 继承AbstractStreamOperator抽象类，实现OneInputStreamOperator接口
2. 重写open方法，进行资源初始化，调用flink提供的定时接口，并注册定时器
3. 重写initializeState/snapshotState方法,需要做缓存，则需要使用到状态
4. 重写processElement方法，将数据缓存到state，到达一定量就输出(collect)
5. 实现定时相关的接口，并实现其中的回调方法

## 调用

使用dataStream.transfrom即可进行调用
