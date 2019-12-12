
# C++ 作业 （11月）

## 第一题

![第一题](图片1.png)
``` C++
#include <vector>
vector<int>  src;// 创建名叫src的int类型的容器

vector<int> src(dst);// 创建一个int类型的src容器，里面的内容与dst容器相同

vector<int> src={1,2,3,4,5,6,7} ;// 创建了一个int类型src容器，里面的值为1,2,3,4,5,6,7

vector <int> src (dst.begin()+2 , dst.end()-2 );//创建的src容器内容是dst的第三个到倒数第二个

vector <int> src(5);//创建src容器包含5个元素，并且对每个元素初始化为0

vector<int> src(7,3)//创建int类型的src容器，有七个元素并且七个元素初始化为3
```
## 第二题
![第二题](图片2.png)
```c++
#include <deque>
#include<vector>
int main()
{
    vector<int> list={1,2,3,4,5,6,7,8,9,10};
    deque<int> list1,list2;
    for(int i=0;i<list.size();i++)
    {
            if(list[i]%2==0)
            [
                list1.push_buck(list[i]);
            ]
            else{
                 list2.push_back(list[i]);
            }
    }
}
```
## 第三题
![第三题](图片3.png)
答：减少为包含十个元素的容器。

## 第四题
![第四题](图片5.png)
```c++
#include<iostream>
#include<vector>
#include<string>
using namespace std;
void change(string s,string oldVal,string newVal)
{
        int i=0;
        string b=s;
        string::iterator iter,iter_;
        string::iterator iter1=s.begin();
        string::iterator iter2=s.end()-newVal.length();
        for(iter=iter1;iter!=iter2;iter++)
        {
                if(s.substr(i,i+oldVal.length())==oldVal)
                {
                        s.erase(s.begin()+i,s.begin()+i+oldVal.length());
                        s.insert(s.begin()+i,newVal.begin(),newVal.end());
                }
                i++;
        }
        cout << s;

}
int main()
{
        string s,oldVal,newVal;
        cin >> s >> oldVal >> newVal;
        change(s,oldVal,newVal);
        return 0;
}
```
## 第五题
![第五题](图片6.png) 

## 第六题
![第六题](图片7.png) 
```c++
#include<iostream>
#include<string>
#include<vector>
#include<numeric>
using namespace std;
int main()
{
    vector<int>a;
    for(int i=0;i<100;i++)
    {
        a.push_back(i);
    }
    int sum=accumulate(a.begin(),a.end(),0);
    cout << sum << endl;
}
```
## 第七题
![第七题](图片8.png) 
```c++
#include<iostream>
#include<string>
#include<vector>
#include<numeric>
using namespace std;
int main()
{
    int a=2,b=3;
    auto sum=[a](int b)->int{return a+b;};
    int result=sum(b);
    cout << result;
}
```
## 第八题
![第八题](图片9.png) 
```c++
#include<iostream>
#include<string>
#include<vector>
#include<numeric>
using namespace std;

int main()
{
   vector<int>list={1,2,3,4,5,6,7,8,9,10};
   vector<int> ::reverse_iterator  iter;
   for(iter=list.rbegin();iter!=list.rend();iter++)
   {
       cout << *iter<< endl;
   }
```
## 第九题
![第九题](图片10.png) 
```c++
#include<numeric>
#include<list>
#include<algorithm>
using namespace std;
int main()
{
   list<string> words={"fox","fox","jumps","over","quick","red","slow","the","turtle","quick","over","red"};
     words.sort();
    words.unique();
    list<string>::iterator it;
    for(it=words.begin(); it!=words.end();it++)
    {
        cout << *it <<endl;
    }
```
## 第十题
![第十题](图片11.png) 
```c++
#include<iostream>
#include<string>
#include<vector>
#include<numeric>
#include<list>
#include<algorithm>
using namespace std;
int main()
{
    typedef pair<int ,string> istring;
    vector<istring> k(10);
    for (int i=0;i<3;i++)
    {
        cin >> k[i].first ;
        cin >> k[i].second;
    }
    for(int i=0;i<3;i++)
    {
        cout << i << ":  " << "first : " << k[i].first << "  second : "<<k[i].second << endl;
    }
}
```
## 第十一题
![第十一题](图片12.png) 
```c++
1.在c的后面加入v
2.在c的后面加入v
3.在每一个v的元素后面依次加入对应c的元素
4.在v的后面加入c的元素
```
## 第十二题
![第十二题](图片13.png) 
```c++
#include <iostream>
#include <fstream>
#include <sstream>
#include <string>
#include <map>
using namespace std;


map<string, string> buildMap(ifstream &map_file) {
	unordered_map<string, string> trans_map;
	string key;
	string value;
	while (map_file >> key && getline(map_file, value)) {
		if (value.size() > 1)
			trans_map[key] = value.substr(1);
		else
			trans_map[key] = value;
	}
	return trans_map;
}

const string& transform(const string &s, const unordered_map<string, string> &m) {
	auto map_iter = m.find(s);
	if (map_iter != m.cend())
		return map_iter->second;
	else
		return s;
}

void word_transform(ifstream &map_file, ifstream &input) {
	auto trans_map = buildMap(map_file);
	string text;
	while (getline(input, text)) {
		istringstream stream(text);    //读取每个单词
		string word;
		bool firstword = true;
		while (stream >> word) {
			if (firstword)
				firstword = false;
			else
				cout << " ";
			cout << transform(word, trans_map);
		}
		cout << endl;
	}
}

int main(int argc,  char* argv[]) {
	ifstream map_file(argv[1]), input(argv[2]);
	word_transform(map_file, input);
	return 0;
}
```
## 第十三题
![第十三题](图片14.png) 
调用了3次

## 第十四题
![第十四题](图片15.png) 
```c++
#include<iostream>
#include<string>
#include<vector>
#include<numeric>
#include<list>
#include<algorithm>
#include<set>
using namespace std;
static int n=10;
 class Employee
{
    public:
        Employee();
        Employee(string nam);
        
    private:
        string name;
        int id;
};
Employee::Employee()
{
    id=n++;
    name="no name";
    cout << name<<endl;
    cout << id << endl;
};
Employee::Employee(string nam)
{
    name=nam;
    id=n;
    n++;
    cout << name << endl;
    cout << id << endl;
};
int main()
{
   Employee employee("aa");
   Employee em;
   
}
```
## 第十五题
![第十五题](图片16.png) 
```c++
int&& r1 = f();           // f()返回右值，因此需以右值引用来绑定
int& r2 = vi[0];          // 变量表达式，以左值引用绑定
int& r3 = r1;             // 绑定了右值引用的变量，以左值引用绑定
int&& r4 = vi[0] * f();    // 返回右值的表达式，以右值引用绑定
```
## 第十六题
![第十六题](图片17.png) 
```c++
#ifndef StrVec_h
#define StrVec_h

#include <allocators>
#include <string>
#include <initializer_list>

// 类vector类内存分配策略的简化实现
class StrVec {
public:
	// allocator成员进行默认初始化
	StrVec() : elements(nullptr), first_free(nullptr), cap(nullptr) { }
	StrVec(const StrVec&);               // 拷贝构造函数
	StrVec(std::initializer_list<std::string>);
	StrVec& operator=(const StrVec&);    // 拷贝赋值运算符
	~StrVec();                           // 析构函数
	StrVec(StrVec &&rhs) noexcept;    // 移动构造函数
	StrVec& operator=(StrVec&&rhs) noexcept;    // 移动赋值运算符
	void push_back(const std::string&);  // 拷贝元素

	size_t size() const { return first_free - elements; }
	size_t capacity() const { return cap - elements; }
	std::string *begin() const { return elements; }
	std::string *end() const { return first_free; }

	void reserve(size_t);
	void resize(size_t);
	void resize(size_t, const std::string&);

private:
	static std::allocator<std::string> alloc;    // 分配元素
	std::string *elements;      // 指向数组首元素的指针
	std::string *first_free;    // 指向数组第一个空闲元素的指针
	std::string *cap;           // 指向数组尾后位置的指针

	// 被添加元素的函数所使用
	void chk_n_alloc() { if (size() == capacity()) reallocate(); }
	// 工具函数，被拷贝构造函数、拷贝赋值运算符和析构函数所使用
	std::pair<std::string*, std::string*> alloc_n_copy(const std::string*, const std::string*);
	void free();                // 销毁元素并释放内存
	void reallocate();          // 获得更多内存并拷贝已有元素
	void alloc_n_move(size_t);    // 将元素移至扩增容量后的新内存地址的工具函数
	void range_initialize(const std::string*, const std::string*);
};

void StrVec::push_back(const std::string &s) {
	chk_n_alloc();     // 确保有空间容纳新元素
	// 在first_free指向的元素中构造s的副本
	alloc.construct(first_free++, s);
}

std::pair<std::string*, std::string*>
StrVec::alloc_n_copy(const std::string *b, const std::string *e) {
	// 分配空间保存给定范围内的元素
	auto data = alloc.allocate(b - e);
	// 初始化并返回一个pair，该pair由data和uninitialized_copy的返回值构成
	return { data, std::uninitialized_copy(b, e, data) };
}

void StrVec::free() {
	// 不能传递给deallcate一个空指针，如果elements为0，函数什么也不做
	if (elements) {
		// 逆序销毁元素
		for (auto p = first_free; p != elements;/* 空 */)
			alloc.destroy(--p);
		alloc.deallocate(elements, cap - elements);
	}
}

void StrVec::range_initialize(const std::string *first, const std::string *last) {
	auto newdata = alloc_n_copy(first, last);
	elements = newdata.first;
	first_free = cap = newdata.second;
}

StrVec::StrVec(const StrVec &s) {
	// 调用alloc_n_copy分配空间以容纳与 s 中一样多的元素
	range_initialize(s.begin(), s.end());
}

StrVec::StrVec(std::initializer_list<std::string> il) {
	range_initialize(il.begin(), il.end());
}

StrVec::~StrVec() { free(); }

StrVec& StrVec::operator=(const StrVec &rhs) {
	// 调用alloc_n_copy分配内存，大小与rhs中元素占用的空间一样大
	auto data = alloc_n_copy(rhs.begin(), rhs.end());
	free();
	elements = data.first;
	first_free = cap = data.second;
	return *this;
}

StrVec::StrVec(StrVec &&rhs) noexcept : elements(rhs.elements), first_free(rhs.first_free), cap(rhs.cap) {
	rhs.elements = rhs.first_free = rhs.cap = nullptr;    // 使右值引用可以安全的被析构
}

StrVec& StrVec::operator=(StrVec &&rhs) noexcept {
	if (this != &rhs)    // 直接检测自赋值
	{
        free();
		elements = rhs.elements;
		first_free = rhs.first_free;
		cap = rhs.cap;
		rhs.elements = rhs.first_free = rhs.cap = nullptr;
	}
	return *this;
}

void StrVec::alloc_n_move(size_t newcapacity) {
	// 分配新内存
	auto newdata = alloc.allocate(newcapacity);
	// 将数据从旧内存移动到新内存
	auto dest = newdata;          // 指向新数组中的下一个空闲 
	auto elem = elements;         // 指向旧数组中的下一个元素
	for (size_t i = 0; i != size(); ++i)
		alloc.construct(dest++, std::move(*elem++));
	free();     // 一旦我们移动完元素就释放旧内存空间
	// 更新我们的数据结构，执行新元素
	elements = newdata;
	first_free = dest;
	cap = elements + newcapacity;
}

void StrVec::reallocate() {
	// 我们将分配当前大小两倍的内存空间
	auto newcapacity = size() ? 2 * size() : 1;
	alloc_n_move(newcapacity);
}

void StrVec::reserve(size_t newcapacity) {
	if (newcapacity > capacity())     // 如果要求分配的空间小于等于已分配空间，不做改变
		alloc_n_move(newcapacity);
}

void StrVec::resize(size_t count) {
	resize(count, std::string());
}

void StrVec::resize(size_t count, const std::string &str) {
	if (count < size()) {
		while (first_free != elements + count)
			alloc.destroy(--first_free);
	}
	else if (count > size()) {
		alloc_n_move(count * 2);
		while (first_free != elements + count)
			alloc.construct(first_free++, str);
	}
}

#endif 
```
## 第十七题
![第十七题](图片18.png) 
因为通过拷贝构造函数生成的ret是一个左值，因此会继续调用当前版本的sorted函数，直至内存泄露。

## 第十八题
![第十八题](图片19.png) 
```c++
(a)string
(b)string
(c)vector
(d)string
```
## 第十九题
![第十九题](图片20.png) 
```c++

#include <iostream>
using namespace std;
class Sales_data 
{
public:
    Sales_data(){}
    Sales_data operator +(Sales_data &a); 
    Sales_data(int a,int b);
    Sales_data &operator+=(const Sales_data &a);
    void display();
    int age;
    int height;
};

Sales_data& Sales_data::operator+=(const Sales_data &a)
{
	age += a.age;
	height += a.height;
	return *this;
}
Sales_data Sales_data::operator +(Sales_data &a)
{
    Sales_data c;
    c.age=age+a.age;
    c.height=height+a.height;
    return c;
}
Sales_data::Sales_data(int a,int b)
{
    this->age=a;
    this->height=b;
}
void Sales_data::display()
{
    cout << age << endl;
    cout << height << endl;
}
int main()
{
    Sales_data a(12,12);
    Sales_data b(24,24);
    Sales_data c;
    c=a+b;
    a+=b;
    c.display();
    a.display();
}
```
## 第二十题
![第二十题](图片21.png) 
```c++

```
## 第二十一题
![第二十一题](图片22.png) 
ld = si + ld是非法的。首先两者类型无法互相转换，因此无法通过重载的+运算符来实现。其次，SmallInt可以转换为int，而LongDouble可以转换为float和double。而int可以与float以及double执行内置加法运算，因此将导致二义性。

ld = ld + si是可行的。因为si在ld的右侧，这就导致了LongDouble的成员函数可以执行。另外，其非成员函数也可以执行，但需要经过一重转换（SmallInt->double），因此会执行其成员函数。

## 第二十二题
![第二十二题](图片23.png) 
有必要，两个功能不影响。

## 第二十三题
![第二十三题](图片24.png) 
```c++
class Max_quote:public Disc_quote
{
public:
	Max_quote(const string& book, double p, size_t qty, double disc):
	Disc_quote(book,p,qty,disc){}

	double net_price(size_t n) const override {
		if(n >= quantity)
			return quantity*(1-discount)*price + (n-quantity)*price;
		else
			return n*(1-discount)*price;
	}

};
```
## 第二十四题
![第二十四题](图片25.png) 
```c++
#ifndef MYBASKET_H
#define MYBASKET_H
#include "Bulk_quote.h"
#include <set>


class basket
{
public:
	void add_item(Quote&& sale) {
		items.insert(shared_ptr<Quote>(move(sale).clone()));
	}
	void add_item(const Quote& sale) {
		items.insert(shared_ptr<Quote>(sale.clone()));
	}

	double total_receipt(ostream& os) const {
		double sum = 0;
		for(auto iter = items.begin(); iter != items.end(); iter = items.upper_bound(*iter)) {
			sum += print_total(os,**iter,items.count(*iter));
		}
		os << "Total Sale: " << sum <<endl;
		return sum;
	}
private:
	bool static compare(const shared_ptr<Quote>& a, const shared_ptr<Quote>& b) {
		return a->isbn() < b->isbn();
	}
	multiset<shared_ptr<Quote>,decltype(compare)*> items{compare};
	
};
#endif
```