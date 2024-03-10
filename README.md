# data-structure
<br>
這邊是簡單整理各種資料結構<br>
並且記錄一些基本的題型以供後續複習使用<br>
可能以後有刷到相關leet code的題目也會一起整理進來<br>
<br>

基本分類
-------------
data structure可以基本分成linear跟non-linear兩種<br>
linear: <br>
* [Array](#Array)
* [Linked_List](#Linked_List)
* [Queue]
  Stuck

  Hash Tables
non-linea:
  Tree
  Graph
<br>
<br>

Array
-------------
array可以是最簡單的資料結構<br>
需要在一開始即知道整體資料大小，以要求連續的記憶體<br>
因此能藉由index直接推算記憶體位置<br>
time complexity:<br>
  search by index: O(1)<br>
  insert element:  O(N)<br>
  delete element:  O(N)<br>
<br>

Linked_List
-------------
而相較於array一次要求一整塊記憶體<br>
linked list可以在一開始不知道整體大小<br>
記憶體位置也不必連續放置<br>
甚至在list中每一個node的資料型態也可以不相同<br>
但在node中需要額外紀錄下一個node的pointer<br>
有單向跟雙向兩種linked list<br>
time complexity:<br>
  search by index: O(N)<br>
  insert element:  O(1) in moving element with searching O(N) first<br>
  delete element:  O(1) in moving element with searching O(N) first<br>
<br>

Queue
-------------
queue相較於array增加了限制: 只能在對首刪除、隊尾增加<br>
帶有FIFO(first in, first out)的特性<br>
以最基礎的實作來說，是在pop最前面的element之後<br>
將後面所有向前move，此為array形式的queue<br>
而為了避免move的耗時過久，後續有Circular Queue跟Linked Queue<br>
經典的題型有<br>
* 楊輝三角形(Pascal’s Triangle)<br>
* 售票排隊問題(Ticketing Queue)<br>
* 迷宮問題(Maze Problem)<br>
更多詳細內容可以參考這裡<br>
<br>
