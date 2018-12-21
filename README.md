# lalala
8/16 在职跳槽 Onsite
第一轮
1. insert a number in ordered array. 应该是 LC35 变形,有duplicates。binary search解决。 2. find the center of mass in a 2D array. 就是找出数字左边sum和右边sum相差最小的那个 position。
第二轮(题库里的高赞题,极度懒惰的面试官会出这题(比如我_(:3TZ)_ delete a node from a doubly linked list. 注意各种边界条件。
第三轮(高频)
设计电梯系统,有若干个电梯,讨论了一些OOdesign和key methods,最后让实现 find_best_elevator。
第四轮(高频)
stock price update,给定的是一系列的entries:symbol(stock_name), price, time_of_price. 自己 设计class和数据结构,要求可以query到任何一只股票的max_price, min_price和latest_price. 注 意后加入的同一只股票的time_of_price可能比先加入的时间更早,time_of_price不是entry_time 。后加进来的同一只股票也可能同样时间不同price,这时认为是更改覆盖前面同样时间的entry。
第五轮
给定一个Quack class。基本上就是一个a stack or queue,已经按升序排好, .pop() will randomly pop from head or tail of this data structure. 要求返利用这个.pop(),返回降序排列的 array。
8/15 return onsite
第一轮
问题1 询问一个点被多少区间覆盖,直接O(n)扫描一遍所有区间,没让写代码。然后要求实现支持多次 查询,求每个查询被多少个个区间覆盖,把区间开头位置+1然后结束位置-1做前缀和即可,预处 理完成后可以做到O(1)查询,也没有让写代码。最后给了一个要求在支持查询的同时还支持随时 插入跟删除区间,想了一下给了个带lazy tag线段树的思路,没让写代码就让我白板上画了一下每 种操作需要在线段树做些什么。这个题目背景一行代码没写,一直在写白板做分析跟解释。
问题2(高频) 只能单向移动求从左往右,求有多少种不同的路径能从出发点到结束点,很简单的组合数学加法 原理。然后问如果强制要求经过某一行怎么办,用了个f[j][0/1]来做DP解决。最后给了个followup ,给一个高度序列,要求从开始点依次通过高度序列中的每一个高度到结束点有多少种走法, f[j][k]来状态转移跟上一问没有本质区别。
￼￼
￼最后5分钟让前面6个想法里,随便选一个写成代码。出于编码简单跟题目复杂度并存的目的写了 最后一个DP的followup,愉快结束。
第二轮
先给了个数字转化成base64的warmup。然后要求把一个binary file转化成all visible text,很容易 想到就把所有的bytes一起用base64(6bits)来表示,如果有余下的bits补0转化。问了好几个细 节问题关于传输完整性以及decoder那头需不需要接受一个关于补0的额外参数。然后说要不把 decoder也写了作为bonus question,写完一共22、23分钟大叔说只准备了一道题,关于各自的 工作跟组闲扯了一会就结束了。
8/14 new grads 电面
第一个是白人小姐姐,上来先聊了一下简历,然后开始做题。。小姐姐说她要copy paste过来一 张图,我当时就预感是tree相关的题lol。。果然贴过来一张n-child tree。
说root node是一个watertank,里面装很多水,然后每个edge上面都标了数字,数字代表需要多 少mins能装满这个child node。第一问是让我自己选个data structure写出来,方便后面做题。 我虽然选的python做题,但是完全不会用python写个tree出来。。。回忆了好久binary tree,然后 她给了好几个hints总算是写出来了(一边给hint一边说dont want to waste too much time on this one....)
然后接下来的问题是写个method来找出最少需要多少mins能把所有的child node都装满水。也是 磕磕绊绊的写完了,dfs。。
(我觉得google真的很喜欢考tree。。。)
第二个是一个白人小哥的声音,很chill,题目很简单。给一个source string 和error_locations tuple list,
source = " !\ndefn foo(x, y):\n..."
error_locations = [(0, 1), (1, 3), (1, 5), ...]
# (line, column), each 0-indexed
然后让 写一个method来把这些tuple变成absolute indices in the source string. 所以刚刚的例子 output 就是 [1, 6, 8]
这题写的还挺顺利的,后来又聊了下简历就结束了。。
8/14 new grads 电面 输入: N个files(每个file都有一个值)
输出:N个files中所有数字的和 提供了:
￼￼
￼1. 一个API: long total(int fileId, int machineId). 这个API派一个machine去读一个file里面的值。 是一个blocking的API。
2. 无限的machines
要求: 最快最快的求出和, 不在乎用了多少machine。
提示:
abstract Thread { void start(); abstract void run(); void join();
}
8/14 new grad 电面
直接上来做题, 给一个dictionary 和 一个word 搜索这个word, 问我用什么数据结构 我说Trie。
就问了时间 空间复杂度, 空间问最优 最坏 和平均 , 平均我是真答不上来。
然后又问什么数据结构 可以优化 时间复杂度 我说Map 。
接下来 要我实现trie tree 写完之后。 问我如何降低memory 我想了一会说 用compressed 就是 不同的字符串 作为一个节点 可是面试官 说很难实现(感觉不是很难啊)
最后 面试官 给出 他的idea 用数组表示整个树, 像是Binary tree, 用2i+1, 2i+2访问子节点,我 说可以用B tree 然后要我写出 用数组表示出来的 B tree 我就蒙蔽了
然后讨论一会就结束了。
8/14 new grads onsite
第一轮 (高频)
给你一个String target 还有一个List<String> dictionary 要求你输出-----所有给target字符串 添加字 符之后等于dictionary 的单词
比如 target ----> google List<goooooogle, ddgoogle, abcd, googles> return List<goooooogle, ddgoogle, googles>
第二轮
开放性design题 要求你随机生成一个Maze(迷宫).
第三轮 ​(LC zigzag原题?)
medium偏向easy题 给你一个String abcdefg 和一个int row = 2 要求你按顺序打印字符 aceg
￼￼
￼bdf
打印结果 acegbdf
如果row = 3 ae
bdf cg
打印结果 aebdfcg
8/14 在职跳槽 电面
直接上来寒暄两句就开始答题。
题目很简单,在一个集合里面找target数字出现过的次数。 example:
[1,2,3,2,5], target=2
answer: 2
[1,2,3,2,5], target=4 answer: 0
解答:扫描一遍数数就完事儿了 follow up: 能不能比O(n)快?
回答:对于unsorted array不行,对于sorted array可以做到O(log(n)) 这大哥貌似对于我的解法不太理解,花了很久又是写例子又是写代码的,最终好歹还是给他说懂
了。最后留了5分钟,随便聊了两句。攒人品求过。 8/13 在职跳槽 Onsite
应该是挂了,最后一轮三姐姐给的题目刚开始就没给什么仔细的说明而且不怎么给hint最后完全 没做出来。题目不细说了但除了最后一轮其他的基本是LC 中等难度.
1. LC 树的遍历
2. 矩阵类题目,本身很简单但小哥问得比较杂follow up特别多
3. 系统设计类似于广告系统
4. BFS 类题目.
5. DFS 类搜索题,不同size的杯子装水
(补充:第五轮应该就是LC365但是给了N个杯子,第二轮小哥说话很分散,follow up就是问在 多个机器上怎么scale。第四轮类似于maze。)
￼￼
￼8/10 在职跳槽 Onsite
第一轮
在一个inventory系统里如何设计一个ID,比如这个id应该由那些信息的hash组成, 如何保证 generation不会重复,分布式系统中如何处理时钟纽斜的问题,这个细节当时并不知道怎么回答 , 但是后来在网上找一找资料就看明白了,类似ntpd原理,总之要有一个negotiation和decision 的环节
第二轮
go game 如何判断某一region是死,四连通还是八连通,如何写test case,进一步followup 如何 半段有几口气,也就是最少用几个子使其变成死棋。
第三轮
2d drawing 有一个画笔和一些线段在一个2d平面上,假设画每条线段需要常数时间,移动笔头需 要常数时间,如何安排写的顺序似的总用时最少。这道题写起来还是挺有难度,我用了贪心利用 最多的首尾相接的节点。follow up:如果画线段时间和移动时间跟距离成正比。
第四轮
tree traverse problem:具体的记不清楚了,但是基本上是post order的变种,问了一下时间和空 间复杂度,并不难。
8/08 在职跳槽 Onsite
第一轮 (近期高频)
飞机场1,2,3,4。 1只能飞到2, 2只能飞到3,以此类推。1到2有很多航班,开始时间, 结束 时间表示,每个航班飞行时间不一样。比如1:15~1:40, 2:00~2:10.... 问最早到达飞机场4的时间。 刚开始楼主感觉是个dp问题,说是不是dp,面试的印度小哥态度很差,一点提示不给,看楼主在 苦思冥想dp,就说我出去一趟,然后出去转了一圈。后来觉得这应该是个backtracking吧。 但是 没有时间了。我觉得思路不对,面试官应该指正一下的。这一轮感觉最不好。
第二轮 (高频)
有个matrix, 从左上角走到右上角多少种方法,只能右上,右下,右三个方向走.
第三轮
n-ary tree, 要求遍历的时候child必须排在parent前面。输出结果存在一个array里面,要求child 存parent 在array里面的index。 要求两种方法做
第四轮
￼￼
￼有个array, 比如0,2, 3, 1. 从某个元素开始,比如2, 跳到index是2的位置,也就是3, 然后 再跳到index为3的位置,也就是1.。。。给你n代表一共跳多少步,k代表起始位置,输出最终跳 到的元素的值。重点在follow up,如果n远远大于array的长度,如何optimize
8/09 new grads 电面
两个StringA,B 要用B来构成A。规则是可以使用任意次B,每次使用都可以从B里挖去任意个字符 比如 A = “ABCACAD”, B="ABCD", 就可以这样构成 ABC*+A*C*+A*D。 如果存在构成方案就 return true。
然后follow up 是 求最少使用B的次数。 如果不存在构成方案则返回-1. 我用DFS做的。
最后压着时间写完的,面试官也就没问怎么优化。感觉自己全程话有点多,每写一行都跟在跟他 交流,浪费的时间有点多。全程交流很流畅,面试官人很好。面试完才想到貌似可以用dp做,心 里有点慌。但是貌似看别人的面经有人没用最优解最后也能拿到onsite?
(结果:已拿到onsite) 8/09 在职跳槽 电面
贪吃蛇。利口上有。 之前没做过。用了30分钟讲思路,不是最优解(应该用deque,只用了queue),代码还差好多 没写完。小哥安慰说,没事,代码不重要,关键是交流和思路。
没想到小哥是认真的,手下留情,第二天约了onsite。 8/07 在职跳槽 电面
LC685,followup 是BST怎么办 8/03 在职跳槽 onsite
第一轮
1. insert a number in ordered array. 应该是 LC35 变形,有duplicates。binary search解决。 2. find the center of mass in a 2D array. 就是找出数字左边sum和右边sum相差最小的那个 position。dp解决。
第二轮 (这是用来面new grads的电面热身题啊?!?
￼￼￼￼
￼delete a node from a doubly linked list. 注意各种边界条件。
第三轮
设计电梯系统,有若干个电梯,讨论了一些OOdesign和key methods,最后让实现 find_best_elevator。
(LZ补充:这个best elevator是讨论出来的,要和面试官一起定义。我想到的一些点首先要是 available的电梯,需要讨论比如超载如何处理,在此之上选择距离user所在楼层最近,电梯需要 travel的路程最少的那个。)
第四轮
stock price update,给定的是一系列的entries:symbol(stock_name), price, time_of_price. 自己 设计class和数据结构,要求可以query到任何一只股票的max_price, min_price和latest_price. 注 意后加入的同一只股票的time_of_price可能比先加入的时间更早,time_of_price不是entry_time 。后加进来的同一只股票也可能同样时间不同price,这时认为是更改覆盖前面同样时间的entry。
(LZ补充:stock price求的事all time最大最小。并且entries有可能是stream,要clarify。第五轮 :实现的就是sort function。只是利用pop来取数。)
第五轮
给定一个Quack class。基本上就是一个a stack or queue,已经按升序排好, .pop() will randomly pop from head or tail of this data structure. 要求返利用这个.pop(),返回降序排列的 array。
8/02 new grads 电面
第一题:给一个sorted list,一个target number,只用get method查找target number. 第二题:给一个int matrix,一个初始power,给start point和end point,matrix里1代表路可以走, 2代表墙不能走,3要减一,4要加一,求问从start走到end可以得到的最大值。
评论区:
第一题,getMethod()其实就是binary search,因为是sorted list。。 第二题,LintCode 1479 变种, 用DFS
8/01 在职跳槽 Onsite 第一轮
给一个硬盘被分成N个区域,实现markUsed(int N) 和findNextNotUsed() 第二轮
￼￼
￼fei 搏 na 妾 + 类似Bus route,但是返回坐车顺序,input的形式要自己设计,即如何表示列车, 如何表示站台, 同时要加入时间
第三轮 设计一个api,求解2个狗是否有血缘关系,每个狗在记录里都有可能有爸爸妈妈,然后如果共享 ,就是一家人了
第四轮
给一个complete tree,每个node都会有index,按照给的index,求出相对应的treenode,并且求 出树的大小
第五轮
acba -> dbcd,给一个start string 问能否转化成end string,主要是Corner case比较多,楼主没 想全,后来在面试官帮助下补全
7/28 在职跳槽 Onsite (已通过)
第一轮 亚裔小哥,以为是国人但感觉英语口音蛮正的,一道无向图的问题,A-B,B-C表示AB和BC直接 相连,AC间接相连,让实现两个函数返回两个点是否直接相连,是否间接相连,楼主直接DFS做 的,followup就是会query很多次这两个函数怎么优化。
第二轮
美国小哥,先问了几个iOS的概念性问题,然后coding是写一个层级性的View description输出。 比如根View上有一些子View,子View又包含子View,让完成一个函数最后打印一个像树一样的 输出格式,也就是DFS做的比较简单。
第三轮 美国小哥,问的题我忘了。。。不过也是DFS就解决的medium级别的题
第四轮 黑人大叔,不是很交流的那种,问的问题很简单,LC电话号码那题
第五轮 国人大叔,让设计一个定时器的小app,写一写MVC的结构以及主要的函数
7/27 new grads onsite
(当天就接到通知说通过了的)
￼￼
￼第一轮
先问了点Java基础知识
Magic Square: given an integer n, build a magic square with size n x n, filled numbers from 1 to n * n, each number can only be used once. And the sum of each row, each column diagonal and anti-diagonal line are same.
e.g., n is 3. Each row, column, and both diagonals all have the same sum 15.
438
951
276
Follow up1: Optimization.
Follow up2: build all possible magic squares for a certain integer n.
第二轮
Rebuild array: given a list of subsequences of an original array, rebuild a shortest unique original array by using the list of subsequence.
e.g., given [[1, 9, 7], [1, 4], [4, 9]], the shortest unique original array is [1, 4, 9, 7]
Follow up: the original array may contain duplicates, return shortest smallest lexicographical order array if multiple arrays can be reconstructed.
e.g.,given [[2, 3], [3, 3, 3]], return [2, 3, 3, 3], 虽然[3, 2, 3, 3], [3, 3, 2, 3]也可以build, 但不是最 小。
第三轮
第一题: Given a string with B*A*C*D* pattern, * means the preceding character can appear 0 or multiple times in the string. Count the number of 'A'.
e.g., "BBAACCDDD", return 2
"BBCDD", return 0
"AAA", return 3
Follow up: what if the string is so large that cannot be fitted in memory?
第二题: Given a dictionary["technology", "nology", "google", "technique", "coo"] and an extra string "chnology", the only operation is to remove some characters from the string. Find the longest one existed in the given dictionary.
In this example, return "nology". Word "coo" can also be formed by deleting some characters, but it is not the longest.
Follow up: The only operation is to add some characters into the string. Find the longest one existed in the given dictionary. In the above example, return "technology".
第四轮
word search I和II的变种 第一题:
￼Given a 2D char board: [['G', 'O', 'O'], ['G', 'L', 'E'], ['A', 'B', 'C']]
and given a word, find a shortest sequence path that contains all characters of the word, the relative order of the word should be maintained. The path can move to any of 8 adjacent cells, but one cell can be used at most once.
e.g1., given "GCB", return "GLCB"
e.g2., given "ABO", return "ABGO" or "ABLO" or "ABEO" e.g3., given "LBC", return "LBC"
e.g4., given "LBF", return empty string
第二题: Instead of one word, given a list of words, find a shortest sequence path for each word. 7/26 在职跳槽 Onsite
第一轮
hashMap with expiration。 不能用自带的HashMap,要自己写。要求 写 put(key, val, time_to_live) , 以及 get( key ) 自己定义输入输出。 面经题。
第二轮 (高频)
currency convertor。给一些list of String[] 比如 “USD", "RMB" , "6.5"这样。 给定两个string,算它 们之间的convertion。面经题。
第三轮
小哥进来又给了一次第二轮的题。告诉他面过了, 让他换题。然后他出了一道extended word的 题。一个extened word , 比如”helllo“, ”helllooo“, 有连续3个相同char,要求输出 这些重复》 = 3的char 的 开始以及结束位置。
”helllooo” 输出 【2,4,5,7】。follow up是给你一个 function isInDictionary(),返回一个单 词是不是在dictionary。要求判断一个给定word,是不是 isExtendedInDictionary。比如:"helllo", 如果 ”helo“,”hello“ 或者 ”hello“ 之中的任何一个在dictionary,就返回 ”helllo“ isExtendedInDictionary 。 题目其实不算很难,估计面试官对题目不太熟,我bug free的code反 反复复让我验证。到follow up就不提引导了,简直是拉后腿。 这轮最后feedback相对差一点,说 我进入题目slow。
第四轮
判断一个单词是不是在char[][] array。八个直线方向,上,下,左,右,左上,右上,左下,右 下。不能拐弯。比LC需要dfs的那道题简单。
第五轮
string encode decode。假定已经有decode,只要求实现encode。举个例子,decode 会 把 ”1dd2Xa" 转成 '1ddaa',’3f3X3‘ 转成 ’3f333‘。 这道题比较tricky,有很多edge case。 第一问比
￼
￼较简单,要求直接把输入转换成countofchar + 'x'+char.第二问,要考虑,aa 转成2Xa反而 变长了, 所以长度短于3的不转。以及如果原string有 ‘2xa' 怎么办。。。。
7/25 在职跳槽 Onsite
第一轮(高频)
面经题,人与自行车。2D grid,人,自行车。讨论了一堆,要求找全局最优配对。暴力解了,时 间刚刚够,没时间给我问问题。
(插:这道题是,一堆自行车和一些人在一个2D的matrix里,要每个人match到一辆自行车,人 和自行车的距离越短越好)
第二轮
一个API: byte[] readByte(int length); 会读你输入的length的长度的bytes,如果读不到了的话会返回null。
readByte() 会从一个(不知道是什么鬼的数据结构,类似于)string的地方读数据。这个 string 的 结构是这样的:
[0,0,1,2][string field][0,1,2,3][string field]
第1,3个 field 的意思是它们后面的string field 的size 是多大。
计算方式是[0,0,1,2] = 0*2^24 + 0*2^16 + 1*2^8 + 2;
你要做的就是获取前面两个 string field 的内容。 写完改了一个小bug,问了问如果读数据的时候突然断网了你的程序怎么办,我说挂了。没时间 给我问问题。
第三轮
写个function,input List<Pair<StudentId, GPA>> list, int K, 返回top k gpa的学生和GPA的list。 面试官oncall挺忙的,没时间给我问问题。
第四轮 (高频) 面经题,汇率。一开始简单聊了一下,然后这人说话好慢,手写题目。没时间给我问问题。
第五轮
实现一个从给你的iterator中筛选偶数的iterator,写test case,generic,多线程。面试官露出蜜汁 微笑。这个大叔在Google 待了11年,做过manager 但是还是喜欢做技术,于是在YouTube 做 tech lead。从一开始的Google Play Music 到现在Youtube Music 他都有参与。本人也是用Play Music 用了很久,看着他本子上的sticker 有种莫名的感动。
(已拿到offer)
￼
￼7/25 在职跳槽 Onsite 可能因为我是转行的,而且用的Python, 题目乍一看都比较简单
第一轮 给一个list的同义词(两两一组),和两个句子,问通过替换同义词,两个句子是否相等。一次历 遍就可以了。第一追问是,如果开始有很多overlap的同义词,比如hello和hi是同义词,hi和hey也 是同义词,要怎么处理。说可以用并查集。第二问是如果同义词现在的长度可以不确定,比如 awsome和very good同义。答dp。这轮感觉比较靠谱
第二轮
求二叉树所有leaf node之和,要用O(1) space. 面试官给我了两次提示才想出来...就是要记一个 PreviousNode,然后根据上一次访问和当前访问的node的关系,决定下一步往哪边走.
第三轮
LC124 写出来之后和面试官一起讨论修复了几个bug。然后追问是如果求最大乘积怎么办,答对 每个子树记录最大正乘积和最小负乘积。
第四轮 一个棋类游戏,方形的跳棋的感觉。先写接口和测试。然后追问是给定棋盘,如果判定你的棋子 能不能走遍棋盘吃掉所有对方的棋子。没想出来什么好的办法,按backtracking做的,最后没有 写完,给面试官口述了一下
第五轮
也是string matching的问题,感觉利口上见过,但是不记得...是给一个单词的字典,和一堆query string. 问query如果只替换(不能增减)一个字母,可以match到字典里的哪个词。我是把每个字 典里的词的每个字母替换成'#'存到set里,然后query也按每个字母替换掉的变种来测试。感觉好 像还可以optimize但是讨论了半天也没讨论出来个所以然。这个面试官连hash string都算进run time了,我也很醉啊。我想说可以用前缀和后缀树,不过好像并没啥用,哭哭。
(Update:已收到offer)
7/24 在职跳槽 Onsite
第一轮
烙印男,typeahead的变种,给前缀输出所有可能,trie秒之。flow up是有一个*怎么办,小卡了 一下然后用了类似two pointer的方法秒之。本来感觉很妥,最后随口说了一句有点紧张,他说没 事,我们每轮都是独立的下面好好发挥吧,言下之意是我表现不好?
第二轮设计 白男,我所有面试中见过最mean的没有之一,先问了一个设计问题,正好是我前几天看过并且和 老婆一起讨论过的,我说着说着突然打断并换题。转问文档查重tf-idf相关的,我没有做过搜索所 以一头雾水硬往下聊,中途被否定了某个模块的两次方法后想求个提示,被残忍拒绝。老哥非常
￼￼
￼酷炫,全程就是在藐视你并且每次回话不超过10个单词,搞的我都想结束面试直接走人。后来中 午吃饭的时候和老婆聊,老婆就是做这方面的,然后说这不就是tf-idf吗然后稍微和我讲了下,才 发现我的思路已经非常接近了,真的是稍微提示一点就解决了,但是老哥就是不肯。
第三轮 国男,态度非常好,全程微笑,题也不难,LC高频hard之一。等我接到fail的通知再来补充,反正 你只要刷了LC这道题没理由不会。
第四轮
LC 773 变种,比原题要难但是思路差不多。不知道是不是国男,感觉有点像ABC,也是态度巨好 ,交谈很给力,最后优化的时候我给了个方法他还说从来没见过但是听起来很创新。
第五轮 烙印女,一开始也是一道LC的hard(是的,我遇到的都是LChard级别的)变种,交流了下问题, 白板上写出了思路,正打算去Chromebook上写代码。打断,换题,让我写了个binary search的 基础题(???),然后让我跑几个test case(???),生生的干掉了25分钟然后留了10分钟 让我问问题(???),最后我看了看Chromebook上留下这个binary search的代码欲哭无泪。
补充:tips,这次都是hard级别的,所以推荐大家白板写思路,键盘写代码,否则两块白板你都写 不下。
7/21 在职跳槽 Onsite
第一轮
白人小哥,两道题
1. 在一个数组里(不一定有序,也不一定只有一个重复,任意数组)找到一个duplicate元素,用 多种方法解决:比如O(1)空间 and O(nlogn)时间啊,排序啊,hashset啊等等。
2. 判断两棵树任意交换一个或多个node的左右节点后是否相等.
第二轮
白人小哥,设计数据结构,设计两个API
1) insert一个interval
2)判断某个值在不在之前insert的所有interval中 要求:用多种方法实现,最后要求code两个call都是logn级别的,不能用C++自带的set啊map等 数据结构。例子, interval有 【1 , 3】, 【5 , 7】, 那么query 4就返回false,query 6 就返 回true
第三轮
白人大树,写一个serialize和deserialize tree(不是二叉树)的方法。和蠡口有点不大一样,规则 想不起来了,但是不难。follow up是给一堆树,返回一个子集,子集里的这些树在某一深度以上 拥有相同的结构,且这个深度是最大的。
follow up 要利用第一问的方法
￼
￼第四轮
国人小哥,find kth element in a tree (logn时间复杂度)
第五轮 面经题,车能有几个group那道题,慢的会block快的。follow-up,加新的车怎么办
加面
第一轮
实现一个special hashmap,每个元素在一定时间内会过期; followup,内存很小怎么办,如何优化,怎么改最开始的code
第二轮
给一个start string, 一个end string,问能不能从start通过一系列独立的变换transfer成end。规则 是只含有26个小写字母,每次操作只能变换一类字母。比如如果把a变成b,那么start string里的 所有a都要变成b。
例子:start - "abc", end - "cde", 变化过程为“abc”->"abe" ->"ade"->"cde",但如果先变成"cbc"以 后就再也变不成"cde”了。
7/18 在职跳槽 Onsite
第一轮​ (本次挂点)
给一个矩阵,每个点有一个高度,从矩阵左下走到右上(可以走四个方向) 让你找到一条路径使得 该路径所路过的高度最小,只需要输出高度。
一开始理解错了题 理解成了( 每次从低点到高点有一个cost 然后高点到低点没有cost 求到终点 最小cost )写完之后小哥表示我不是这个意思。连忙改完 最后没时间检查了。最后我的思路是每 点存路过该点的目前最大高度 然后bfs 当bfs到任意一点目前所走最大高度小于该点存在高度时才 继续bfs 其他情况剪枝。
后来下来想了一会儿 二分枚举高度+dfs应该是可以解决这道题的 跟LC 778 一样 不知道有没有更 好思路
第二轮
面经 (LC好像也有 不过略有不同)
一群人坐在板凳上, 给新来的k个人安排座位让每个人离旁边的人尽量远
第三轮
LC 220系列 123
没刷过3 当场想了个bst 应该还行
￼
￼第四轮
上来聊天15+分钟..然后给了一到大水题 数组平衡index 就是在数组中找到一个index 他的左边和 跟右边和相等
第五轮
人超级好 极度放水的给了一道 最大子数组和..follow up 问内存放不下怎么办
7/16 在职跳槽 电面
(近期高频,LC 857。果然狗家面过以后马上就加入LC了 hhhh)
N个candidates,每个candidate有工作的时间和期望的薪水 比如 A 10 months 100$ B 20 months 400$.
1. 要求是必须至少满足每个candidate期望的薪水
2. 要求所有人的工资/时间是一样的
比如 如果我要同时雇A和B 因为要满足条件1,所以要付B 400$ 因为要满足条件2, 所以要付A 10 * (400/20)= 200$.
给一个candidate数组,求出需要K个人的时候最少需要花多少钱 7/16 new grad onsite 加面
(Update:没有通过)
1. 面筋题,一堆牌,每张牌上有分,有正有负。你跟你朋友轮流从面上抽,每次必须抽1到3张。 你跟你朋友都很牛逼,总是依据当前牌堆里的使用最佳策略保证自己能抽到最多的分。问你你先 抽,你能最多得多少分。 一道比较凶猛的1维dp,没看过不太好想。很不幸,楼主面试前没看过。小哥一路提醒,就差帮 我写代码了。。最后跌跌撞撞写了出来,面试过程基本等于给我讲了一道题。
2.去年年初的面筋。模拟雨滴打湿道路。
雨滴宽度1cm,道路宽度100cm
设计一个api,boolean isWet(double drop) 当道路完全打湿的时候返回true,其他时候false。 drop 是雨滴的中心,比如drop = 12.942 那他就会打湿 12.442 到13.442。 给你一串雨点streaming。每个雨滴都会call一下这个函数。 思路是每个雨滴建个interval,看跟之前的有没overlap,有就删除合并。 这题提了个O(n)面试官说不急着写。。优化一下。
￼￼
￼那就只有log(n)了。。搬出了java 的内建神器TreeSet,实现log(n)。python的话,感觉不太好 搞。。
7/18 电面
最近的高频题,给两个file,计算汇率,类似 LC 399 例子:
file1:
USD, GBP, 0.69 \\USD = 0.69 * GBP
Meter, Yard, 1.09
file2: USD, Yard
output:
USD, Yard, 0.69*1.09
我说我把file1分成两个list, 完全转化成了LC399。。。
follow up1: 问我average时间复杂度是多少,我说O(n),她问我n是什么
follow up2: 小姐姐一看时间还有两分钟,问我如果file2的输入有billion个,但是memory很小呢?
7/17 new grads onsite
第一轮
高频题,LC399 直接union find(区别是他了两个 input file, 第一个input file 类似“USD”"EUR" "0.669", 第二个input file 是查询“USC” “RMB” 自己要想好如何处理input file, 因为查询次数可能 很大 我直接用的UF, 同时我讲了 dfs bfs的时间复杂度,以及UF的好处)
第二轮
connected 4 game 。给你一个play (k,n,i) 返回嬴或者输。 自己定义 数据结构,类。问题抽象成 一个数组, k是连续的石子,N是数组长度,i是每次你放石子的位置。当你放一个石子到数组里 ,使连续的石子长度大于等于K 就返回true 否则返回false。 我上来给了O(K)的解法,然后跟 面试官讨论更好的解法,最后没搞出来 写了最初的算法
第三轮
高频题, 一个map分为n层,每层都m个node, 每个node有值,每一层跟下一层的node是full connected,edge的值不一定相同,求从第一层到最后一层的mini cost DP解决, 也是高频题(区别的需要自己定义input data)我最后写的是 一维DP
第四轮
没见过的题 给一个String “a{1,2}b{3,4}d”输出 “a1b3d”,"a2b3d","a2b3d","a2b4d" 我说可以把string 抽象成树的结构 用dfs 或者bfs解决。 如果数字过多bfs可能会overflow(我最后用bfs写的,当时 脑子抽风)这轮三哥一直 ok great ok great 听的我都虚得慌
￼￼
￼第五轮
超级爆炸的一轮 (国人男)上来没给例子,白板上也没解释,直接口述题(很长一段)(当时脑 子宕机,挺累的)然后花了能有十几分钟才理解题意。backtracking问题. 给你很多node(他说是Apple)每个Apple之间有关系 friend 或者 enemy, 你有N个袋子,每个 袋子能装无限多个苹果,限制条件是每个袋子装的苹果只能是friend 不能是enemy 要你输出最后所有装袋子的可能(这题我最后没解出来,虽然写了 backtracking 但是代码肯定有 问题.... 思路都没想明白 代码就更惨不忍睹了)要求所有Apple都装进袋子 我用的HashMap<Integer,int[]>代表每个袋子最后装的苹果,Integer是袋子的index, int[]代表 APPLE.
7/16 在职跳槽 Onsite
第一轮
每个node有一个weight,和一个level number,node只会指向self.level+1的node,每个边有向且 有weight,问从第一层到最后一层的最小值。直接把第一层的每一个跑一边dfs就好了。需要剪枝 优化。follow up输出最小值的路径。
第二轮 dp常见题,LC上的,题号忘了,就是两个人分别从两边拿钱币(钱币价值不同),问第一个人能 不能赢。这之前考了一个字符串处理,挺简单的忘了。
(插:这道题最优解是O(1) 2333333
第三轮 输入一个数组,代表每个人的得分。输出一个数组代表给每个人的奖励的钱。最少要给每个人一 块钱的奖励。如果某个人的分比他的邻居高,则得到的奖励必须也比那个邻居高。follow up:1. 如果有同分的情况 2.O(n)实现
第四轮 常见题,实现一个iterator的iterator。里口上好像有。
第五轮 河上有n*n个石墩子,石墩子间有桥(完全连通的),靠岸的石墩子和岸之间也有桥。一个坏人过 来把一些桥破坏了。1.输入破坏后的图,找到从河的一边能否走到另一边。2.坏人对每个桥的破 坏的几率是50%,问破坏后能走到另一边的几率。
7/13 在职跳槽 Onsite
鼓起勇气面了一次狗家,在职跳槽好累,快要坚持不下去了。。遇到的题其实都不算难,准备了 很久很心虚的图论unionfind什么的其实都没考,但还是没有面好挺遗憾。。不过也算是努力了, 就这样吧
￼￼
￼在sunnyvale面的
第一轮:
一堆string排序,包括a1.doc, a1b.doc, a2.doc, a12.doc 还有版本号1.2.1,100.2.1,反正就是都 要排序,我也不知道为啥。。。这么大众化的题我中了邪就是没写完还写了bug出来。。。雪崩
第二轮:
设计一个ReqLogger class, 有start和end函数,用户call start(int id, timestamp starttime)来开始 一个request,然后call end(int id, timestamp starttime)标志这个request结束,然后要一个write 函数把所有已完成的request按照start time的排序写入disk。需要注意就是可能一个开始很早的函 数迟迟不结束。学完了之后又问了一堆multi user同时使用的会􏰀成的multithreading和share memory的问题
第三轮: 面经题,只能向右、右上、右下走,那么左上角到右上角有多少种走法,太急于写代码,没想清 楚就下意识开始写,然后第一次还写错了,后来冷静了一下,面试官又提示了一下才写对。。。 提醒大家,看到面经,你以为你会了,其实你并不一定真的会了。。。最好写一下代码再run几个 test case确保万无一失真的懂了,不然像我这样遇到原题都没做好,当场真的会很崩溃,如果不 是面试官比较冷静比较和善,心态很容易崩盘。。follow up,有一系列点必需依次经过,有多少 种走法
第四轮:
一堆赋值方程,比如x1=x2+x3, x2=x3+x4, x1=x3+x4。。。。(都是a=c+b形式的),如果某个 变量被赋值之后还没被用到过就又被新的方程赋值了,之前的值没有被使用就被overwrite了,那 么之前那个赋值方程就是useless的。例如上面的例子,x1=x2+x3就是useless的。写一个 function,给你list of 方程(面试官很贴心的给了一个方程object,里面存这个方程里的a,b,c, 比较好处理),然后让你输出list of useless方程。这个题没见过,面试官给了hint才做出来。
第五轮:​LC 01matrix 找四个1组成矩形那道题,一时没有想出最优解,写了一个基础的解法,面 试官说最优解确实不太好想,就出了个别的题。lc issimilartree那个题,recursive解的,然后问时 间复杂度,懵逼。。。在他的提示之下想出了recursive call的时间复杂度相当于一个tree的叶子节 点个数,他又说其实这个题并不是所有叶子节点都走到了呀,卒。。。他其实最终目的是想说我 写的code改变一下recursive call的顺序,还有提高performance的空间。。。这个是真的从来没 考虑过的问题,崩的也不亏。。而且他是那种愿意教你正确答案是什么的面试官,所以还向他学 到了,感觉还挺赚的
7/12 在职跳槽 Onsite
第一轮
第一道给个2^16次方的二维矩阵 每次以田字形切割 顺序如下 12
03
￼
￼然后抽出每个小矩阵 再次切割 比如4*4的矩阵 就会长这样
5 7 9 10
4 6 8 11
1 2 13 14 0 3 12 15
现在矩阵是2^16 * 2 ^ 16的 给你一个x, y坐标 让你求那个点的数字是多少, 比如在4*4里面 ( 3,3) = 8 (3,0) = 14.本文原创自1point3acres论坛
做法 经过回家后大神提醒
应该是DFS 从顶向下 每次旋转去找 退出条件是 x == i , y == j的时候
这题我被完全整懵了 当时想反了 我以为是一道数学动规题 一直从小往大的往上找规律推方程 结 果很悲剧. more info on 1point3acres
而且是用的二分法找range 应该铁挂了 :(
第二轮
字符串转为二叉树 输入是一个字符串
一个数组 数组里存着加减乘除的顺序 可能是+-*/ 可能是* - + /之类的
比如给你个1 * 9 - 3 +2 *7. 让你转成
+ /\ -* /\ /\
*327 /\
19 普通递归dfs大家都会
第三轮 OOD
设计个log start,finish finish后 输出log id跟内容 但finish的时候 如果start前面还有start 就不能输 出。直到没有pending了 就全输出
比如
start(1, time1) start(2, time2) start(3, time3) finish(2, time2)
￼finish(3, time3) finish(1, time1)
输出1,2,3
为啥 因为finish2得时候 前面还有个1 被start过
finish3的时候 2虽然没了 前面还有个1 被start过
做法是Queue + map我当时多用了一个queue 面试官提醒说不用 让我循环map就可以
第四轮
比较简单简单 ,就是给你个汇率 输入有关系跟输出想要的关系 A-D = 3
B-C = 4
D-B = 2
求A-B C-A A-Z
像A-Z没有的就输出个null把输出1屡成图 用BFS做就可以了
第五轮(高频,已加入 LC 857)
是个生做的题给你个list 里面存着每个人 每个人有最低工资要求 跟人力质量 要让每个人happy 那么要让list里每个人工资就要跟人力质量成比例
比如 A($1, 2) B($1, 4) 你给A一块钱 为了让B开心 你就要给B两块钱 那么问整个list的人全被hire的最低cost是多少
这个我的做法就排个序
因为有corner case
A($1, 1) B($10, 1) 人力一样钱要的不一样得
A($1, 1) B($100, 2) 乘以比例依然达不到人家最低要求的
所以排序的时候要按照人力排 人力相等时 把最低工资从大到小排
然后循环的时候 加人力的比例累加 把出现case1或者2的时候 更新最小工资 最后返回 比例和*最 小工资
7/10 在职跳槽 电面
LRU cache。不是数量限制,每个数据都有时间限制。过时间就删掉。 follow up:怎么删掉无效的数据。优化。priority queue。
￼
￼6/30 在职跳槽 Onsite
第一轮 (google题库高赞题)
最近比较常见的 matrix从左上走到左下(方向: 下 左下 右下)一共多少种走法 follow up1: 必须经过一些点到达 一共多少种走法
follow up2: 必须越过某column ci 到达左下 一共多少种走法
第二轮
第一题是实现wrap()这个api, 具体可见 ​https://commons.apache.org/prope ... va.lang.String-int- 第二题是实现一个array setAt(i, v) get(i) setAll() 都是O(1)复杂度
第三轮
输入一个整数n 输出叶子树量为n的所有full binary tree
第四轮
输入一个数组一个inverter的class inverter,这个class里有方法可以转换一个list(转换:正变负 负变正)输出这个转换后的array中正数最多的那个array
(类似最近LC的一道contest题?)
第五轮
给一个adjacent map 形状是环状,按顺时针或者逆时针输出这些点. visit 1point3acres for more. follow up 输出所有可能的结果
6/27 在职跳槽 Onsite
第一轮
数组里有没有a[p]<a[q]<a[r], p<q<r。没见过,蒙了,一看就知道要用DP,琢磨了半天,小哥说不 用想的那么复杂,然后说出straightforward的DP解法,写代码,算法、代码都出错
第二轮
pure virtrual 的 class Iter, 俩member function Next() hasNext(),给定一个Iter的数组a,按照 a[0].next, a[1].next, ...的顺序(如果a[k]没有next了就跳过)构􏰀一个iterator,里口有原题?需要继 承Iter定义一个新class,又蒙了,小哥提醒下好不容易写完,中间还出个bug
第三轮 用电话按键编码26个大写字母,怎么编码怎么解码自己设计,很open的问题
第四轮
￼￼￼
￼长度是m的山洞,各个点的高度是h[j],入口在h[0]处,有n个箱子宽度1高度b[k],最多能把几个箱 子塞进山洞里,greedy method,先往洞的最深处塞箱子,捡能塞进去的最大的那个塞,不确定 是不是最优解,follow up是n非常大怎么办
第五轮 张三出去旅游,给你他的飞机票,找出从哪个城市出发,到哪个城市结束的,转换成有向图,出 度大于入度就是出发点,很容易证明,
第二题 LC 270
06/25 在职跳槽 Onsite
第一轮
给一个网叶 树 结构,自己定node的结构, 数有两种node,一种是tag node 另一种椰子 node, text只存在椰子 node里面,给两个数,比较两个数中餒容是否相通
比如
<a><b>hello</b><c>world</c></a>和
<a><b>hellow</b><c>orld</c></a> 对应的数的内容都你好四界,所以这两个数的餒容是相通的
Follow up 如果最后生成餒容太大累存放不下怎么办
写一个椰子节点 iterator,iterator 按照钱序遍历的顺序依次返回椰子 node
第二轮 (高频) warmup 算低k个斐波那切
给一堆汇率 pair比如 美刀/人刀 = 6.7 美刀/欧刀 = 1.2, 人刀/日刀 = 100 问任意给两个火必
比如 人刀/欧刀 = ? 人刀/日刀=?这个题后来有人说是散酒久,确实是,但是最好的做法是冰茶集 变形,刚才看有人也面了这题,说用图秒了,图做起来也没错,但是不是zhui佳解法
第三轮 (高频)
第一题,给一个制服串banana 有另外一个紫附串 cololo,他们相思 原因很直观 问题是给两个制服串,盘断他们是否相思
Follow up 现在有一百万个志符串,给定一个制服串,问这一百万个制服穿里面是不是有制服穿根 给定的制服穿 是similar这个解法就不说了,不算太难.
第二题
给一个制服串是键盘上的按键操作,比如
abc<-<-d <-是闪除操作,那么这个制服穿最后就是ad 问给定一个制服穿,问最后这个制服穿是什么 如果不仅有闪出,还有达写
比如
￼
￼CAPSabc<-<-CAPSd 接过就是Ad 用碓解
第四轮 给一个呆子,呆子里有k中砖投,每种砖投的个数是Nk个,现在随机从呆子里拿砖投,拿出来以 后不放回,写一个class 实现这个功能
假设 n1 + n2 + ... + nk = N
第一种解法是用树组来存所有,那么空间复杂度O(N) 取转投复杂度O(1)
Follow up
对空间复杂度不满意
存每中转头的个数,然后岁机生成一个1到N之间的数来却定是哪种砖投 空间复杂度O(k) 取转头复杂度O(k)
Follow up
对空间复杂度满意 对时间复杂度优化
用二份索引树 + 二份搜索可以达到 (log(n))^2的取转头复杂度 用瓶亨而叉树变形可以实现log(n)的取砖投复杂度 自己感觉这个题非常好从简单到难,面试官不停地在follow up,感觉面试官心里要的就是log(n)的 ,其他的他不是很关心
第五轮
有小王 肝6h, 宫紫6块,小李肝3h, 弓子15块,小赵3h,宫紫9块,每个人的瓶均宫紫是1块/重头, 5块/重头, 3块/重头 最后选择的人根肝多长时间没有任何关系,只要求选k个银,付的弓子最少,要求给附给每个选择 的k个人中最高的瓶均弓子
如果选3个银,就必须给每个人附5块/重头, 总的就 刘十
若果选2个银,
选小王和小木子就是5 *(6 + 3)= 45
选小木子和小找就是5 * (3+ 3) = 30
选小汪和小找就是3 * (3 + 6) = 27
所以如果选择两个银,最优应该选小汪和小找
6/20 在职跳槽 Onsite
第一轮
给你一堆log,里面每个人的cpu usage,起始时间和结束时间, 每个人的peak usage。 会议室2 的做法。 做完了以后写test case。然后简单问了一下问数据量很大怎么破。 然后说题目改了,之 前说的是在这个时间段里面是cpu usage是恒定不变的, 现在变成线型增长的了,start time的时 候是0, end time 的时候是log里面的那个值,然后问同样的问题。。。我第一反应还是往会议室 2上面套,说那就看要多精确,比如说要精确到分钟,那就把之前的时间段拆成分钟级别的。小哥 将信将疑的看着我,让我码出来来看看。写完了,小哥拍完照,看看时间,给我说,其实你这个 做法不太对,你想想,如果两个时间段t1, t2 overlap的话,最大值只可能出现在什么地方。 我一
￼
￼想,说只可能出现在t1.endtime 或者t2.endtime的地方,小哥说,那就对了嘛,然后就走 了。。。。
第二轮
问我对context free grammar 熟不熟悉。 我说并不知道,小姐姐表示非常好,就喜欢考不知道 的。大概意思就是,给一串字符,比如说“abc”,grammar 会有一个 mapping,比如说a -> "ab", b -> "c", c -> "";然后问给一个string n 个iteration后,string 会变成什么结果。 基本上就是brute force一下。然后小姐姐问,你这个东西的空间复杂度是多少,我说这个很难讲,得看你这个 mapping是什么情况。她说,那好,如果我说不太关心最后string会变成什么样,我只关心最后有 多长。 然后我就犯傻逼了,抠了半天脚,没有想出来,耽误好多时间。估计小姐姐都崩溃了,其 实方法就是只记录string中的每个character的个数,就能generate下一个string各个character 的个 数,最后加一下就完了。码完了以后,基本上没有多少时间了,又问了一个问题,说给我的一个 string,判断通过一定iteration后,能不能变得stable。比如说上面那个abc,因为a会变成ab,b会 变成c, c会变没有,所以这个是stable的。然而想了一会儿,并没有想出来,时间就到了。
第三轮 三哥面,国人大哥shadow。出去上厕所的时候,国人大哥问我上午如何,我说一般般。大哥安慰 我说,没有关系,面挂一轮也无所谓。在此谢过大哥了。问题是,你有一系列窗口,有些窗口会 有重叠,让计算出每个窗口最后会有百分之多少展现出来,自己设计数据结构。我大概的意思就 是,先假设这些窗口,只有两两重叠的,写了一个method。然后在三哥的提示下处理两个以上重 叠的,大致的想法就是,比如说你已经算了0 到i个窗口,现在来了i + 1 一个窗口,你只要保证前 面0到i个窗口中,没有两两重叠的,那算i + 1的时候,就不会有两个以上重叠的。所以做法就是 每次在处理i + 1 的时候,先处理0到i,发现有重叠的,就split成多个窗口。最后code写得一团糟 ,估计挂了。
第四轮
东欧大姐,问题很简单 ​https://www.geeksforgeeks.org/tree-isomorphism-problem/​。 我照这个上 面的方法码完以后,大姐表示可以,让我开始优化。很显然我没有get到大姐的点,我觉得这个算 法基本上已经很优化了,不知道该如何改进。感觉大姐也应该是暗示到极限了,才明白大姐的意 思是,程序的最后一行递归的时候,因为要分别 node1.left 和 node2.left, node1.right 和 node2.right比, 或者node1.right 和node2.left, node1.left和node2.right 比。所以这里还可以优 化,就是在对于每一个node,只要做一些约束,比如说,左边的val比右边小,就能够只用左子树 和左子树比,右子树和右子树比。赶紧改完code,照完相,走了。
第五轮 (高频)
ABC 小哥和大黑哥, 问了一个拿纸牌游戏, 纸牌上面有值,比如说 100, 1, -1, 2, 200, 1. 然后两个人轮流拿,直到拿完。 但是每次只能拿从左边数起的前三个,但是如果你要拿第三个 ,就必须前两个都拿了,你要拿第二个,就必须第一个也拿了,大家都最优策略,问最后第一个 人能拿多少分。dfs 加 cache做了。 又问了一个bst相关的题,不难-
￼
￼6/19 在职跳槽 Onsite (面试通过了)
第一轮 Cornell的学姐,题目不难,背景是假设现在有个火车站台(可以看做一维的array)上面已经有一 些人站着,站着的点就算作occupied,想让新进入站台的人能够站到一个离现在站台上所有其他 人都最远的点,请问要怎么解决。 我简化了一下,其实就是梳理一下当前站台上人与人之间的gap,以int[2]的方式存到 priorityQueue里,每次进来人就去pq中gap距离最大的,讲这个gap二分成两个小gap加回pq follow up是如果给你的初始站台是空的,问题会不会简化?当然会,可以直接按照二分法安排进 来人的位置。
第二轮 abc小姐姐,问的题不难,而且好像是别人最近告诉她的她自己也没太明白...所以大半时间是我
在试图讲给她听。题目是 现在有一个图,包括很多node, 其中一些node 是可以pass的,一些是 deadend,有一个表示终点,然后要求
1.判断能否有从指定node开始到达终点的path
2.如果有请输出path
1 (start) /\\
3 4 2 -----6 (dead. (dead) |
5 (终点)- 图大概就是这样,很简单...
第三轮 这轮我完全忘了..记忆空白
第四轮
LC 843 全程讨论多,边讨论变写code,还有怎么利用已有code
第五轮 大概就是个华容道游戏,全程在跟我讨论怎么表示board,每个方块,不同的方法表示board的当
前情况需要多少空间字节。知道最后才问我,给定一个初值值怎么解这个游戏,我差点崩溃了..说 dfs可以解,大概就是记录当天board的状态,然后找当前board有几种可能的move方式,然后根 据这几种方式move生成新board这样dfs下去知道发现一个解
6/09 在职跳槽 Onsite (Update:offer已签)
￼￼
￼第一轮
1. 设计股票价格的记录系统。只观察一支股票的价格,实现几个function:
void update(double price, int timestamp) 更新/修正/删除股票价格,其中timestamp大部分时间是 递增的,但是有时候发现过去的记录有错误,所以会对过去数据修正或invalidate。对过去数据修 正是指input argument中的timestamp是一个已经记录在案的timestamp,让price为function新提供 的price;invalidat时候function argument中的price为-1,删除timestamp对应的记录
double max() 返回历史最大值
double min() 返回历史最低值
double current() 返回最近一次的记录。
针对各种情况进行实现和算法复杂度讨论。(大量更新?大量查询?invalidate很多很少?etc.)
第二轮 (高频)
1. 王位继承。初始只有一个king,king会有孩子,孩子还能生孩子。实现几个function: void birth(String parent, String name) 父亲名字和孩子名字,生个娃
void death(String name) 此人要死
List<String> getOrder() 返回当前的继承顺序,string array/list
讨论得知,每个人的名字是唯一的,继承顺序符合如下规律: 假设王有大皇子二皇子三皇子,大皇子有长子次子三子,那么继承顺序是王->大皇子->大皇子长 子->大皇子次子->大皇子三子->二皇子->三皇子 死掉的人不能出现在继承顺序里,但是如果上面例子中大皇子死了,只需把大皇子移除,原始继 承顺序保持不变:王->大皇子长子->大皇子次子->大皇子三子->二皇子->三皇子
三个function会被反复调用,实现function细节。
2. 纯算法问题,不求代码。二维平面上有一堆水平和竖直分布的线段,给定每个线段的两端点坐
标,找出两两相交的线段的相交点,计算使用所有相交点,能构成多少正方形。 (插:找交点是扫描线O(nlogn),构成正方形类似于LC长方形?)
第三轮
1. 直线上给定一些点,再从直线上找出一点,使得该点到其他每个点的距离之和最短。 我以为要代码求解,完全无从下手,点也都不是整数点,后来告诉我是median,就是看我知不知 道。
2. 用实际问题包装起来的算法题。
产品中要monitor service response time,假设已经收集了大量数据,给定percentile的定义:如 果说20ms的响应时间是90 percentile,代表收集的数据中90%的response time小于20ms,10% 的response time大于20ms。同理,如果是说50 percentile,就是50%小于,50%大于。分析如何 处理数据从而得到percentile。(这里假设了已经收集了大量数据,但是我们仍然就大量采集数据
￼的系统环境进行了分析。最终还是回归到已经收集好的情况下)假设数据量大到memory无法存 下,怎么处理?不考察系统设计,只根据实际需求在数据和算法层面进行优化。
(最终写的代码不是针对静态数据,而是一直在接收新的数据,而且数据总量大到memory无法 存下)
第四轮
1. 0和1的grid,1是墙,0是路,从左上角走到右下角,最少多少步。
2. followup: 现在说能把grid中的一个1变成0,问新的最小步数是多少步。
第五轮 (高频) 好像在地里见过,扫地机器人问题。给出了扫地机器人的interface,要让扫地机器人扫遍整个房 间。房间设计成一个m*n的grid,0是路,1是障碍,实现几个function。
move() 朝着机器人面对方向移动一格
turnLeft(int k) 逆时针转动k次
turnRight(int k) 顺时针转动k次
clean() 打扫机器人当前格子
cleanRoom() 发动机器人清理整个房间,清扫任务的entry function。. from: 1point3acres
难点主要在如何把move turn和clean的function扦插到具体的算法实现中。 5/27 在职跳槽 Onsite
(已通过)
1 LC 399
2 给了一个pad, 就是26个字母的顺序排列。 给个单词,让你算出如何能打出单词。简单的DFS 3 给了一个树,大隐最长路径。 2D sum range
4 系统给一个log输入,每一条是 时间, ID 和 words, 统说话字数最多的人。
5 一个树有一个edge是多余的。找出并移除。 (很简单的一道题,当时候迷糊了)
5/25 在职跳槽 Onsite
Update:考虑到每轮都只做了一道题,而且第二轮还卡壳了,本来以为狗家这回没戏了,谁知面 完后周三通知我过,周五hc和team match也通过了。狗家在我心中属于女神级公司,所以自然就 从了
第一轮
￼￼
￼先礼仪性的问了下简历,然后直接跳到题目,题目是设计一个黑白棋游戏的后端API。规则就是 如果落子之后可以将同一条线上对方的棋子两头都堵住,那么对方的棋子就会变成你的棋子。比 如某一行原来是 ABBB,我走一步变成 ABBBA,那么最终结果就会是AAAAA 需要设计和实现API完成判断落子是否合法,是否有玩家取得胜利,落子之后新的棋盘情况,以 及一个提示玩家可选落子位置的API。在墙上写了落子合法性判断和落子后新棋盘更新,之后口 述了剩下API的设计和实现方法
第二轮 (高频) 题目是在一个坐标系里给很多离散的点,找到一条线将所有点分成两个数量相等的集合,不用考 虑基偶性或者多个点在一条线上的特殊情况。 这题似乎和人工智能的分类器之类的有点关系,可惜楼主基础不牢一开始基本完全懵逼。提出了 个O(n^3)的算法,然后只能想到用heuristic来优化。 面试官只说了句可以更快,然后就等我自由发挥,在楼主卡壳五分钟尝试了各种天花乱坠的解法 后,问了我一个问题:总共有多少条符合条件的线? 在这个提示下楼主提出了一假设:过任意一点,一定能找到另一个点将坐标系中其余的点分成两 个数量相等的组(不知道怎么证也来不及证,但是直觉告诉我是对),基于这个假设之前那个算 法的实际复杂度是O(n^2),结合heuristic实际情况会更快 最后终于在时间结束前把代码写出来了
第三轮
题目是利扣上面的skyline problem变种,场景换了,但核心没变。写完了主要讨论用什么数据结 构存题目中的点最高效
第四轮 (高频) 题目是有一张长凳一开始分散的坐着一些人,每个新来的都想坐在最宽敞的一段的中间位置,问 如何模拟这一过程。follow up是如果有多个长凳该怎么办?以及如果长凳的数据太大,内存装不 下又该怎么办? 这轮是楼主面试自我感觉最好的一轮,做完题终于能有剩余时间和面试官聊天问问题
5/24 在职跳槽 Onsite
第一轮
给一个rate limiter的基本设置: class RateLimiter {
static final String REQUEST_PER_PERIOD = 100; static final String PERIOD_SEDONDS = 60;
public static boolean allow(int timestamp) {
}.
}
设计一个rate limiter的allow函数来判断是不是允许这个request通过,还是限制这个request。 allow函数的参数是request进来的timestamp。这里面的REQUEST_PER_PERIOD表示一个时间
￼
￼duang只允许100个request,PERIOD_SEDONDS表示这个时间段是60秒。这两个值是直接给定 的。
第二轮
给一个build system, 比如:
A: []
B: []
C: [A, B]
D: [C]
E: [A, B, C].
意思是build C 需要A和B, D需要C,E需要A,B,C。现在让你求如果我动了某一个文件,我需 要rebuild哪些文件。比如我改了A,那我就要rebuild C和D和E。让你设计一个系统,并且定义一 个函数 给定改动的一个文件,来获得需要rebuild的文件。这个函数不需要考虑rebuild的顺序,只 需要给出所有需要rebuild的文件。
第三轮
LC503,follow up是如果data是streaming data, 要怎么改代码和设计输出。
第四轮 给一个8X8的板,定义船是这个8X8板里的某一行的一部分,或者某一列的一部分。比如8X8的板 里,从(0,1)到(0,3)是船,从(3,4)到(7,4)是船等。这样两个人玩游戏,A先把所 有的船画好,另一个人B并不知道A把船画在哪里。然后B开始射击这个板。目标是要把A的船击 沉。如果B经过多次射击后大中了某艘船全部的点(如果船是从(0,1)到(0,3),那么如果 射击到了(0,1),(0,2),(0,3)),那么船就被击沉了。需要面向对象设计这个游戏。 有两个函数一个是int shoot(int x, int y),另一个是boolean hasBeenShot(int x, int y)。 int shoot(int x, int y)函数是B用来使用的,需要实现:
1. 如果本次射击打到了之前射击过的点 throw exception. 2. 如果打到了板,并不是船,返回 0
2. 如果打到了船,返回 1
4. 如果船沉了,返回 2
boolean hasBeenShot(int x, int y)函数需要实现返回这个点是否被射击过。
第五轮 (高频)
汇率转换问题: 给一些初始化的汇率转换 (USD, CNY, 6.2), (CNY, JPY, 12),让你求比如USD -> JPY的汇率什么的。这个地里很多面经都有,就不赘述了。
5/18 在职跳槽 Onsite
第一轮,狗屎运撞本科校友了,真心感谢校友抬了一手,coding地里出现过,设计converter,两 个api,第一轮状态真心差,多亏了校友了估计
1. 输入是两个symbol和rate,存起来, e.g. ¥,$, 6.3. 2. query是给两个symbol,return rate
￼
￼第二轮,亚裔,题目是cousin marrage,三个api: 1.addParent,输入三个person的id,后两个是第一个的parents 2.addcouple,输入两个person的id,这两个人是couple 3.countCousinMarrage,根据目前已有信息计算有多少cousin marrage,定义是有相同的
gradparent,但是没有相同的parent. 我上来各种和面试官纠结乱伦的事情,自己可不可以和爸妈有孩子什么,可不可以重婚,最后我
们约定不可以。。。
第三轮,ABC?bold word in string,给一个string,和一个list的words,要求把string里面所有出
现的word加bold的html tag<b></b>
第四轮,三姐,意外的很nice,题目解释很清楚,给hints,题目是给一个先递增再递减的integer array,要求
1.找min
2.找max
3.找target number. more info on 1point3acres
第五轮,看上去还是亚裔?第一题忘了。。。第二题是给一个二维数组代表google的campus,然 后有人和自行车在不同位置,要求计算人到自行车的距离,先考虑一个人一个车,followup是多 个人多个车,最后followup问了没时间没让答,感觉是很经典的stable marriage?可惜当场也没来 得及说。
5/16 在职跳槽 Onsite
第一轮​ 国人妹子 (高频)
有几条公交线路 : 1. a->b->c -> d 2. a-> c->e->f 3, f->s->n : 问从某个起点 : 比如a 到 某个 终点,比如n 的最少转车次数。简单的bfs ,有某个地方妹子不太明白 ,讲了半天 ,妹子点点头 ,不知道是不是真明白了 ,anyway ,代码留给她了 ,估计应该问题不大
第二轮​ 老美。。。。 忘了面试题了 。。。。 不难,写的时候 ,还没睡醒 ,在某个很简单的地 方卡了半天 ,老美略有点不耐烦 ,写完后我问写的还行么大哥 ?? 老美说还行吧 ,你面这level 差不多写成这样也就行了。不知道真行假行。。。
第三轮​ 国人小哥,这一轮比较坑, 首先他晚到了 10分钟大概 , 先面了到 简单的题 , abc -> bdf,a map成e,b map成d,c map成f,多个字母可能map到同一个字母,比如a,e都 可以map 成 f
followup : 在第一步map 完之后 ,比如 a map 成 b 之后 ,原字符串变成了 bbc , 这时候再把b map 成d ,就破坏了之前的map ,问怎么办 ,我说中间加一层 ,把b map 到d 这个过程改成b map 到4 , 4 再 map 到d ,小哥说ok ,那能不能写一个函数 ,判断我们在map 的过程当中需要 返回是否要加这中间一层的过程 。。。。。。。。 我去啊 。。。。 我跟他确认题确认了至少半 天 , 最后就10分钟写了 ,写出个bug 。。。 但是关键是小哥自己没看出来这个bug 。。。。。
￼
￼这一轮我在面试之后直接向recruiter 反应了一下 ,说面试官来晚了 ,能不能帮我向hiring committee 说一下 ,取消掉这轮或者加面 ,recuirter 说他要向面试官确认下 ,我在想他要是跑 去和面试官确认 ,会不会让面试官感觉我在投诉他的样子 ,然后给我个negative feedback ??? 不知道有没有人碰上过我这种情况 ,最后是怎么个结果 ??
第四轮​:简单的maze II , bug free ,白班跑了几个test case ,国人小哥表示认可 第五轮​:number of binary search tree I && II ,跑了test case ,国人小哥表示很可以 ,面完了
还把我送出来 ,用中文聊了聊 ,他表示这一轮面的蛮不错
话说 ,碰上国人面试官 ,面完之后聊聊中文扯扯家常 ,真的很能拉进距离 。。。。
5/10 实习电面
第一个,纽约美国小哥,就一个问题,twin strings
就是给你一个string 的array, 如果一个后面三个字母是另一个前面三个字母,则成为twin string 用hashmap搞定的
follow up:如果很多怎么搞
第二个,好像也是个老美.
上来先问什么是binary search。我说需要先sort,然后blabla 他说既然先sort,如果给一个打乱的array,问用binary search找所有的树可以找到几个 我先写了个nlogn的算法,后来要求logn,这时候网断了......不过我也不太会写.
follow up是如果不是用中点,而是任意的点(randint来判断大小),哪些些一定会找到
第三个是刚刚面的
给一组log_message的list
比如 [(‘A’, ‘info’), (‘B’, ‘warn’), (‘A’, ‘warn’), (‘C’, ‘error’), (‘A’, ‘error’), (‘B’, 'info")] 给一个max_out, 比如 3
则输出 [(‘A’, ‘info’), (‘B’, ‘warn’), (‘C’, ‘error’)]
如果是5
输出 [(‘A’, ‘info’), (‘B’, ‘warn’), (‘A’, ‘warn’), (‘C’, ‘error’), (‘B’, 'info")]
5/07 在职跳槽 Onsite (没过HC,加面SETI了)
电面:
Online top-k frequent word in a string stream
Onsite第一轮
￼￼
￼先问了一些java Collection的基础知识,然后让自己implement一个Set class,要求4个O(1)时 间的API: add, contains, remove, getRandom. 挺简单的OOD,因为getRandom也要常熟时间, 所以每次删除就把最后一个元素和被删除的swap就可以
第二轮 (高频)
面经题,找了半天 LC 好像没有,e.g. “hololo”可以encode为“banana”,就是两个string里的char 需是一一对应的encoding关系,不能一对多也不能多对一,这轮卡了一下,开始用的一个Map+ 一个Set,面试官让不用Set怎么做,其实就是把两个string的role交换一下,然后followup问要是 有millions of original string,给一个encoded string问能不能从millions of string里面一个encode 来,说了MapReduce的做法,时间就到了
第三轮
两个很大的数字,用LinkedList表示, 比如3->2->1->0,然后要做乘法,输出也是LinkedList,就 brute force模拟了手算的过程,分析了时间复杂度m*n
第四轮
先聊了一会儿web application的架构,然后开始做题,要写一个online的单位转换器,可以添加随 时新的转换关系,e.g. 'USD' -> 'RMB' = 6.8, 'RMB' -> 'JPY' = 10之类的,然后也要支持query, 难点在于转换关系可以传递也可以逆转,所以就用了hashmap存adjacent list,然后讨论了应该在 每次添加新的关系的时候遍历并且compress path因为config应该没有query的call频繁,小哥表示 同意,就开始写两个API,path compression就用DFS做了
第五轮
找binary tree的最长increasing path,root到children的,类似利口298,递归秒了,然后不用递归 怎么做,BFS秒了,然后分析了runtime space requirement就是看recursion tree的depth
5/04 在职跳槽 纽约Onsite
第一轮
给一个black list,里面都是ip address,ip address里可能包含wildcard字符 "*", 问如果现在有一 个ip address,它是否在black list里。和面试官交流后,确认ip address都是合法的,而wildcard 只会出现每个地址的最后,直接用trie做了。
第二轮 给一个数组代表一个跑道,数组上的数字表示为车􏰁。如果前面的车比后面的车慢,则会block后 面的车,这时会形成一个cluster。比如[1, 2, 3]是一个cluster, [2, 3, 1, 2] 这里有[2, 3] 和 [1, 2]两 个cluster, 而[2, 3, 2, 2]这里有1个cluster, 要求输出每个cluster的size. 这题的本质其实就是找出第 一个比前一个cluster开头的数小的数,其中第一个cluster的开头肯定是数组的第一个数。Follow up是如果现在在数组上插入一个数,这个数比数组上的任意一个数字都大,问每个cluster的size 会有什么影响。显然这时插入数组的开头会形成一个新的cluster,而其他位置都不会影响原来 cluster的size。
￼
￼第三轮 (高频)
面经题,长子继承制的OOD设计,要实现void birth(String parent, String child), void death(String person)和void getOrderOfSuccession() 3个API。
第四轮 面经题,已知screen的高和宽,给你最小和最大的fontSize,要求给定一个string,将string用竟可 能大的fontSize显示在screen里。已知两个API getHeight(int fontSize), getWidth(char c, int fontSize),可以得到每个character在不同fontSize下的高和宽。和面试官交流后,确认string可以 拆分成几行显示在screen中,先提出暴力解法,然后用二分法优化。
第五轮 给定一个范围,比如1-100,输出所有翻转180度后还在这个范围内,且不等于它本身的数。这个 是leetcode 248的变形。
4/18 在职跳槽 onsite CS master + 5年工作经验
1. 保险箱密码生成:高频面经题,不需要最优解,hashmap记录已经访问的 + 带restart的搜索 2. 扫地机器人:需要用一个hashmap来建坐标系地图,dfs
3. LC750变种,最大的面积:hashmap + 扫描线思想
4. 二维数组index转为一维数组的index。。。
5. 还有一个...不太记得了 (Update:已拿offer)
4/13 new grads onsite
第一轮
第一题 sorted array of numbers x,比如 [1,3,4,5,6],给一个二元一次函数 f(x) = Ax^2 + Bx + C,要求生成 x^2 的数组,也要 sorted。
第二题一个4X4的字符矩阵,一个单词字典。要求找到所有出现在矩阵中的连续的单词。连续指 的是周围八个方向。
a b c d. From 1point 3acres bbs
efgh
atef
reag
出现的单词有 eat area tee 等。应该是因为时间不够了,只讲了一下思路,讨论了一下复杂度。
第二轮
￼￼
￼地里那个 1-650 flap 是不是产生误会那题,比如 18->81。follow up 是 1-10000000
第三轮
一段墙,0-L,给 (xi, yi) 的部分涂颜料,涂很多次后求没有被涂颜色的地方。所有数都是 double follow up 1:L不是很大,xi yi都是整数,怎么减少复杂度
follow up 2:现在涂颜料是按顺序涂的,(xi, yi, ti),每次涂都有一个时间戳 ti。求最后每段墙的最 后被涂的时间,没被涂则时间为-1。
比如(1, 2, 0), (3, 8, 1), (5, 10, 2),则结果是(0, 1, -1), (1, 2, 0), (2, 3, -1), (3, 5, 1), (5, 10, 2) ...
第四轮
一堆点(以 Array of (x, y) 的形式),找到形成的长方形的面积最小那个。长方形的边都是垂直或 平行于坐标轴的。
follow up 要求找到的长方形内部不能有其他的点
4/12 new grads onsite
第一轮(高频) 最长的假期,一个人坐飞机去不同城市,每个城市在特定时间的假期长度不一样。问可以享受的 最长假期。Followup:输出itinerary。记得有原题。
第二轮 删除一个树里的几个节点,返回森林的根节点。这题卡了一会,搞清逻辑了最后还是写出来了。
第三轮
在一个sorted array中找第k个缺失元素。比如[2,3,5,7], k = 0: 返回4, k = 1:返回6. 这题写出来 了但是没有时间查bug。
第四轮 在一个由从1到n元素组成的n+1长的数列中输出任意一个有重复的元素。这题需要写出四种写 法。并且会考察test case。我以前一直没注意过testcase,就考官的思路是,test case要覆盖程 序的所有branch。这点非常重要。
第五轮
phd thesis。深入聊一个work。面试官没有做笔记,感觉主要考察深度和表达能力。
4/10 new grads onsite
第一轮: 给一个person类,包括一个发消息的delay时间和一个下属的list,输入一个公司CEO,输出当 CEO发消息之后,所有人都收到消息的时间。
follow up1:如果一个人可能有多个上级怎么办?
￼￼
￼follow up2:按收到消息的顺序输出人,CEO是第一个(follow up1的条件取消,一个人只能有一 个上级)
第二轮:
第一题,LC 674 第二题,用数组实现queue,开始输入一个queue的大小,然后实现add和poll操作。
第三轮: job类包含user,开始时间,结束时间,使用内存量,输入一个job的list,输出每个user使用内存 的峰值。follow up:如果数据量很大怎么办。
第四轮: 输入一个排好序的数组,输出任意一个数量超过数组长度1/4的数。 先O(n)解决。优化一下,到O(logn)
4/10 在职跳槽 Onsite
第一轮
input: 一些字符串words, 一个目标字符串, 要求返回words里 包含了所有目标字符串里的所有 char 的词中最短的那个。
eg: words = [study, haha, stone, school, star, store] target = "rts", 需要返回 的词是star, 因为 star 包含了所有rts, 同时也是最短。
follow-up: 多种方法优化这道题的方法, 楼主先排序 (要求写出查找的平均时间复杂度) 楼主还答了可以把words 存成 s: study, stone, school, star, stor; t : star, stone, store..... 这样的 map, 好处是我们查找的时候只需要看target里出现过的char所对应的词,然后找并集,在目标字 符串很小的情况下有可能会省很多时间。
第二轮 用preorder和postorder建树,这道题出来时我说好像没有inorder是做不出来的,然后聚了个例子 ,面试管说那就假设总是有left subtree的,然后楼主用recursion写了。完了分析时间复杂度,问 怎么优化(hashmap 存一边postorder里的val 对应的Index).
第三轮
类似LC 359 但不一样的是这个api不能存query, 不负责接收query,不负责发送,只是会每1秒让n 个isAllowed() 返回true. 这题我当场有点懵,我就说了那就写一个count和clear, 然后每秒清零 count。但这样做会􏰀成每秒前10个可以,会形成每秒一个峰值。面试官问可不可以有一个更平均 的分布,我说那就每1/n秒返回一个true, 然后清零... (我知道这样做很笨,但当场没有想到更好的 方法。面试官一直强调说不能存任何和query有关的东西(除了计数),只负责yes or no然后保 证这个rate的正确性),写完码答了怎么unit test
第四轮
这个姐姐是我面得最开心的一轮,她整个人很活波,一直笑,让我放松了很多。
给一个char stream, 有next(), 和hasNext(), 两个API。 给一些字符串作为目标字符串。要求每当 char stream里出现目标字符串任何一个词,就打印这个词。
￼
￼比如目标 'abc, att, bba, bc, abce', 然后我们对char stream call next, 出来的一些char 是 t, a, b, c, e, t.... 我们需要打印 abc, bc, abce 这题用字典树,比较麻烦的是需要在字典树里存多个指针,然后每次出来一个char,就写一个 Loop来更新所有现有的指针就可以给了。
第五轮
LC 815 这题我面试前一天看过一眼,因为当时是乐扣最新的一道hard,(其实一点不难),但前一天只 是想了一下,没有练习码。不过面试官说出考题的时候还是很激动的,感觉比较胸有成竹了吧。 做完后写了三个unit test, 白哥看了时间,还有10多分钟,他让我写了两个javascript里的call back function 给他看一下,问了一下我平时遇到bug怎么debug之类的就聊完了。
(Update:过了HC)
3/08 在职跳槽 Onsite
(Update:已拿offer)
1. int array, 所有數字都連著出現兩次,只有一個數字出現一次。找出只有一次的數字
2. 給matrix, 1表示有金礦, 0表示沒有。找出最大的礦坑。(找出最多幾個1連在一起)
3. 一張長凳上面散著坐了一些人,新來的人要坐在最大的間隔中間。假設新來n個人,給出這n個 人要坐的位置。延伸,架設長凳上一開始完全沒坐人,怎麼知道第n個來的人要坐哪
4. 給一string array, 找top k frequent string
5. 輸入法,給一串拼音,給出有哪些種字的組合
￼
￼
￼
