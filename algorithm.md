
## 语法
* 数组拷贝: list.copy(); list[:]
* 判非空: not POINT
* 入栈出栈: list.append(VALUE); list.pop()
* 常用变量名: ans(answer答案), stk(stack栈)


## 题解
#### 排序算法

#### 树

#### 贪心算法

#### 动态划归

#### 双指针

#### 链表
* 环的判断(141, 142)
总结来说就是, 快慢指针快指针的速度是慢指针的两倍,当需要判断入环点时, 引入第三个指针设置在头部,此时慢指针的新指针的交汇点即是入环点
> tips: 使用同起点, 使用do-while循环
* 链表相交(160, LCR023, MST 02.07)

#### 图
* DAG(有向无环图)深度优先遍历(797), 经典递归
```python3
def allPathsSourceTarget(self, graph: List[List[int]]) -> List[List[int]]:
        ans = []
        buffer = [0]
        def dfs(index):
            if index == len(graph) - 1:
                ans.append(buffer.copy())
                return
            for i in graph[index]:
                buffer.append(i)
                dfs(i)
                buffer.pop()
        dfs(0)
        return ans
```
