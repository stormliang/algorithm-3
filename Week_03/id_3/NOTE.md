# 学习笔记
本周做了两道图和堆的easy题目
## LeetCode_703
这个题,5月4号做了一天,在反复翻书并且查看网上的其他解法之后写了出来.  
做这个题目,首先必须要知道struct{}里面填什么,明确是使用堆的,但是我还是一上来就把结构体填入了类似二叉树节点的数据,比如:  
```
struct{
    int val;
    KthLargest* left;
    KthLargest* right;
}KthLargest;
```
结果可想而知,怎么写怎么别扭,后来就去看discuss中的讨论了,只看了第一行我就明白了,为啥花了一上午时间怎么都写不出来了,第一行长这样:
```
typedef struct {
    int* arr;
    int length;
    int size;
} KthLargest;
```
其余的实现,无非是拆分子问题,逐步实现每一个小功能,然后把他们拼装起来  

### **总结**  
- 解题时,第一步就要确定使用的数据结构,正确的数据结构可以事半功半
- 实现时,分别采用了节点的上溯和下滤,这个是array带来的好处
- 依然要重视问题的边界,比如这个函数的实现了哪些功能,输入的边界是什么,输出的边界是怎么,什么时候会异常等等,全面的考虑问题
- 想好再写,否则只会做无用功;画图和伪码

## LeetCode_997
这道题目很简单,先用一个邻接矩阵实现了之后发现runtime > 7.3%, memory usage < 100%, 于是就在考虑优化的事情,把矩阵改成了两个数组,并且在读入trust的时候往数组里面填值,可惜的是时间消耗下降不明显.  
暂时没找到更好的方法来解.