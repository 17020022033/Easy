## W8    01
标准模板库：STL       
容器：可容纳各种数据类型的通用数据结构，是类模板      
迭代器：可用于依次存取容器中的元素，类似于指针      
算法：用来操作容器中元素的函数模板      
容器分类：      
顺序容器：vector，deque，list                 
关联容器：set，multiset，map，multimap                       
容器适配器：stack，queue，priority_queue                 
顺序容器简介                 
容器并非排序的，元素的插入位置与元素的值无关                 
有vector，deque，list三种                 
vector，动态数组，元素在内存连续存放                 
deque，双向队列，在两端增删元素具有较佳的性能                 
list，双向链表，不支持随机存取                 
关联容器简介：                 
元素是排序的                 
插入任何元素，都按相应的排序规则来确定其位置                 
在查找时具有非常好的性能                 
set容器，不允许相同元素，multiset中匀速存在相同元素                 
map/multimap                 
map中存放的元素有且仅有两个成员变量，一个名为first，另一个名为second，                 
map根据first值对元素进行从小到大排序，并可快速地根据first来检索元素。                 
map和multimap的不同在于是否允许相同first值的元素                 
容器适配器                 
stack                 
栈，是项的有限序列，并满足序列中被删除、检索和修改的项只能是最近插入序列的项。后进先出。                 
queue                 
队列。插入只可以在尾部进行。删除、检索和修改只允许从头部进行。先进先出。                 
priority_queue                 
优先级队列，最高优先级元素总是第一个出列。                 
定义迭代器：                 
容器类名：：iterator     变量名;                 
迭代器可以执行++操作。                 
```ruby
#include <vector>
#include <iostream>
using namespace std;
int main(){
     vector<int> v;
     v.push_back(1);v.push_back(2);v.push_back(3);v.push_back(4);
     vector<int>::const_iterator i;//常量迭代器
     for(i=v.begin();i!=v.end();++i)
              cout<<*i<<“,”;
     cout<<endl;
```
