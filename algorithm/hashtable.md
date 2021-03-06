# 哈希表


### 拉链法 (Separate chaining with linked lists)
通过哈希函数，我们可以将键转换为数组的索引(0-M-1)，但是对于两个或者多个键具有相同索引值的情况，我们需要有一种方法来处理这种冲突。一种比较直接的办法就是，将大小为M 的数组的每一个元素指向一个条链表，链表中的每一个节点都存储散列值为该索引的键值对，这就是拉链法。

### 线性探测法 
线性探测法是开放寻址法解决哈希冲突的一种方法，基本原理为，使用大小为M的数组来保存N个键值对，其中M>N，我们需要使用数组中的空位解决碰撞冲突。

	已知一组关键字为(39，49，54，38，44，28，68，12，06，77)，用除余法构造散列函数，用线性探查法解决冲突构造这组关键字的散列表。
	解答:为了减少冲突，通常令装填因子α<l。这里关键字个数n=10，不妨取m=13，此时α≈0.77，散列表为T[0..12]，散列函数为：h(key)=key％13。
    由除余法的散列函数计算出的上述关键字序列的散列地址为(0，10，2，12，5，2，3，12，6，12)。
    　前5个关键字插入时，其相应的地址均为开放地址，故将它们直接插入T[0]，T[10)，T[2]，T[12]和T[5]中。
    　当插入第6个关键字15时，其散列地址2(即h(15)=15％13=2)已被关键字41(15和41互为同义词)占用。故探查h1=(2+1)％13=3，此地址开放，所以将15放入T[3]中。
    　当插入第7个关键字68时，其散列地址3已被非同义词15先占用，故将其插入到T[4]中。
    　当插入第8个关键字12时，散列地址12已被同义词38占用，故探查hl=(12+1)％13=0，而T[0]亦被26占用，再探查h2=(12+2)％13=1，此地址开放，可将12插入其中。
    　类似地，第9个关键字06直接插入T[6]中；而最后一个关键字51插人时，因探查的地址12，0，1，…，6均非空，故51插入T[7]中。
     
### Hopscotch Hashing

采用了Hopscotch_hashing算法，其思路见这个[http://en.wikipedia.org/wiki/Hopscotch_hashing](http://en.wikipedia.org/wiki/Hopscotch_hashing])
这是一种线性探测hash算法的变形，主要目的是为了提高查询速度。原始的线性探测算法在key较多的情况下探测次数过多，而这个算法的目的其实就是减少探测的次数。
他的步骤主要是这么三个步骤：

1. 首先检测映射到的bucket，看它是不是被占用，如果未被占用那就直接使用
2. 如果已被占用，那么采用线性探测法探测到位置pos
3. 如果pos的位置离bucket的位置大于给定的阈值H，那就调整这个上面的位置，使得这个H－1的bucket上出现空槽，如果没有空槽，resize哈希表然后再次进行尝试。

memcached有所采用，不过性能好像不是很好，主要是expand hashtable的过程变得代价很大，而且expand的时机的选择变得更加的不确定，而且expand的过程中必须得上锁，期间几乎不能处理其他的请求，如果不expand bucket的话，可以有比较不错的处理性能的情况，所以这个过程和memc3的cuckoo hashing比较类似，它确实也舍弃了expand hash这个后台处理线程，看来线性探测法在这个expand上确实很难做到最优。


### Cuckoo Hashing


### Google Sparsehash


### 参考资料
[从证券交易所的需求来谈谈HashTable](http://chuansong.me/n/2035214)
