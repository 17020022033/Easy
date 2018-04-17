## W8    01
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
set、map属于标准关联容器，使用了非常高效的平衡检索二叉树：红黑树，                 
插入删除效率比其他序列容器高是因为不需要做内存拷贝和内存移动，而直接替换指向节点的指针即可。                 
set只含有Key，而map有一个Key和Key所对应的Value两个元素。                 
set和vector的区别在于set不包含重复的数据。
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
容器类名：：iterator     变量名;                 
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

迭代器：可用于依次存取容器中的元素，类似于指针            
随机访问迭代器，可以进行双向迭代器的所有操作            
以及 p+= i p-=i p+i p-i p[i] p<p1 p<=p1 p>p1 p>=p1            
W8 02
vector deque是随机访问            
list set map是双向迭代器            
stack queue不支持迭代器            
有的算法 比如sort需要通过随机访问迭代器来访问容器中的元素，那么list及其关联容器就不支持该算法。            

find查找区间是`[first,last)`用==判断相等            
返回值如果找到是被找到的元素，找不到就是last    
```ruby
#include <iostream>
#include <set>
using namespace std;

int main()
{
  typedef set<int>::iterator IT;
  int a[5]={3,4,6,1,2};
  set<int> st(a,a+5);
  pair<IT,bool> result;
  result=st.insert(5);
  if(result.second)
    cout<<*result.first<<" inserted"<<endl;
  if(st.insert(5).second) cout<<*result.first<<endl;
  else
    cout<<*result.first<<" already exists"<<endl;
  pair<IT,IT> bounds=st.equal_range(4); //lower_bound upper_bound
  cout<<*bounds.first<<","<<*bounds.second;
  return 0;
  }
//Output:
//5 inserted
//5 already exists
//4,5Program ended with exit code: 0
//
  ```
