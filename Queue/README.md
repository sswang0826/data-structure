#Queue
<br>
queue相較於array增加了限制: 只能在對首刪除、隊尾增加<br>
帶有FIFO(first in, first out)的特性<br>
以最基礎的實作來說，是在pop最前面的element之後<br>
將後面所有向前move，此為array形式的queue<br>
而為了避免move的耗時過久，後續有Circular Queue跟Linked Queue<br>
<br>
<br>

Array Queue
-------------
此為典型的queue，當有element pop時會做以下操作
Index | 0 | 1 | 2 | 3 | 4
--- | --- | --- | --- | --- | --- 
element  | a0 | a1 | a2 |   |  

進行pop之後<br>

Index | 0 | 1 | 2 | 3 | 4
--- | --- | --- | --- | --- | --- 
element  |   | a1 | a2 |   |  

Index | 0 | 1 | 2 | 3 | 4
--- | --- | --- | --- | --- | --- 
element  | a1 | a2 |   |   |  

可以看出會有O(N)的move動作，因為會有以下兩種變形<br>

Circular Queue
-------------
解決以上方法，最簡單的是加入front與rear兩個pointer<br>
並允許rear移動到front之前，如下所示<br>

Index | 0 | 1 | 2 | 3 | 4
--- | --- | --- | --- | --- | --- 
element  |   |   |  a0 | a1  |   
pointer |   |   | front |   | rear

此時要push進2個element，結果如下<br>

Index | 0 | 1 | 2 | 3 | 4
--- | --- | --- | --- | --- | --- 
element  |   |   |  a0 | a1  | a2
pointer | rear |   | front |   |  

Index | 0 | 1 | 2 | 3 | 4
--- | --- | --- | --- | --- | --- 
element  | a3 |   |  a0 | a1  | a2 
pointer |   | rear | front |   |  

但由於此時如果再push element，可以發現front與rear的位置重疊<br>
而queue非empty的情況發生<br>
因此這邊需要額外保留一格不能使用<br>
full()的條件也改為 (rear+1) % queue_size == front<br>
<br>
back()的index改為 (rear - 1 + queue_size) % queue_size<br>
以避免rear在index==0時發生意外<br>
<br>
size()的條件改為如下
```
  if (rear < front) {
    return (rear + queue_size - front) % queue_size;
  } else {
    return rear - front;
  }
```

linked Queue
-------------


