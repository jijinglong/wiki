- [Start](#start)
- [Primitive Data Type](#primitive-data-type)
  - [Float](#float)
- [Composite data type](#composite-data-type)
  - [Struct](#struct)
  - [Function](#function)
    - [Default Value](#default-value)
    - [Overloaded](#overloaded)
  - [Class](#class)
- [STL](#stl)
  - [Map](#map)
- [Algorithm](#algorithm)
  - [Prime](#prime)
  - [Fast Power](#fast-power)
  - [GCD](#gcd)
  - [Union Find](#union-find)
  - [Sort](#sort)
- [IO](#io)
  - [Multi Cin](#multi-cin)
  - [Getline()](#getline)
  - [split](#split)

## Start

使用const，不要使用#define

``` cpp
#include <iostream>

int main() {
    using std::cout;  // 命名空间，解决冲突的一种手段
    std::cout << "Hello, World!" << std::endl;  // endl立即刷新输出流到屏幕，'\n'则不具备这种特性
    cout.put('a');  // 旧版cout会将字符常量存为int，字符变量存为char，现在可以不使用
    return 0;
}
```

## Primitive Data Type

### Float

``` cpp
cout.setf(ios_base::fixed, ios_base::floatfield);  // fixed point
float f = -0.2e-20;  // e表示浮点数，数字中不能有空格
float tub = 10.0 / 3.0;  // 3.333333，7个3是精确的
tub = tub * 10000000;  // 33333332 7个3之后就产生了偏差，所以注意float和double的精度

float a = 2.34E22f;
float b = a + 1.0f;
cout << b - a;  // 0， 因为float类型只能表示前7位，修改第23位对这个值不会有任何影响
```

## Composite data type

多使用get()而不是getline()，getline读完后并不知道是读到了末尾还是由于数组已经填满。get()使得错误检查更简单些，检查第二个get()是否为换行符即可。

``` cpp
const int max = 10;
int arr[10] = {0};  // 对数组部分初始化，会将其他值也初始化为0
int arr2[max];  // 数组的大小只能用常量值

char str0[] = {'w', 'o', 'r', 'l', 'd'};  // 不加'\0'不是字符串
char str1[] = {'w', 'o', 'r', 'l', 'd', '\0'};  // 加'\0'表示字符串
char str2[] = "world";  // 另一种字符串初始化方式

char str[20]
cin.getline(str0, 10);  // 最多读取9个字符，余下的空间在尾部添加空字符。在遇到换行或读取指定数目后停止读取。读取并丢弃换行符
cin.get(str0, 10);  // 不读取换行符，而是留在输入队列中
cin.get();  // 不带参数，可读区下一个字符，即便是换行符

string s;
getline(cin, s);  // string与字符数组不一样的句法
cout << s.size();

cout << R"(f24\f234)";  // raw字符串，R"(开头， )"结尾。"与(之间也可以加其他字符，但是结尾必须对应加同样的字符
cout << R"xx(hello)xx";
```

### Struct

``` cpp
struct ListNode {
    int val;
    struct ListNode* next;
};
struct ListNode n1;  // c不能省略struct
ListNode n2;  // c++可以省略struct

struct inflatable {
    char name[20];
    float volume;
    double price;
};
inflatable guest = {  // 初始化方式
        "Glorious",
        1.88,
        29.99
};
```

### Function

#### Default Value

必须从右向左添加默认值

``` cpp
int harpo (int a, int b = 4, int c = 5);  // valid
int chico (int a, int b = 6, int c);  // invalid
```

#### Overloaded

与函数多态是同一回事，但我们通常用函数重载，意思是可以有多个同名函数，关键是函数参数列表，也称为函数特征标（function signature)

### Class

``` cpp
// 头文件
// filename: MyClass.h
#ifndef MYCLASS_H_
#define MYCLASS_H_
class MyClass {
    const int x = 10;  // 错误，类声明只描述了对象的形式，在创建对象前，没有用于存储值的空间
    static const int y = 10; // 可以
    int name;
    int other;
    void f();
public:
    MyClass();  // 默认构造函数，若有了一个构造函数，则必须添加默认构造函数，否则编译器会提供默认构造函数，当然，若给任意构造函数的所有参数都提供默认值也可以，为所有参数都提供默认值的方式更好
    MyClass(int nm, int o = 0);  // 构造函数，不用声明返回值类型，可以设置默认值
    ～MyClass();  // 析构函数，必须没有参数，为使用new的成员delete设计的
    void show() const;   // 只要函数不修改调用对象，就应该声明为const
    void hide();
    friend int operator+(int a, const MyClass &m); // 友元，不是成员函数，因此不能用类成员运算符调用，但与成员函数有相同的访问权限
};
#endif
```

``` cpp
// 实现
#include "MyClass.h"

MyClass::MyClass() { // 默认构造函数
}

MyClass::MyClass(int nm, int o) {  // 构造函数
    name = nm;
    other = o;
}

MyClass::~MyClass() { // 析构函数
}

void MyClass::show() const { // 只要函数不修改调用对象，就应该声明为const
    f();
}

void MyClass::hide() {
    show();
}

inline void MyClass::f() {

}

int operator +(int a, const Myclass &m) {  // 定义友元，不用MyClass限定符，也不用friend关键字
}
```

``` cpp
MyClass mc = MyClass(1, 2); // 显式调用构造函数
MyClass mc(1, 2); // 隐式调用构造函数
MyClass mc;  // 使用默认的构造函数，当且仅当没有定义任何构造函数时，编译器才提供默认构造函数（没有任何参数的构造函数），当为类定义了构造函数后，程序员就必须为它提供默认构造函数。

// 下面的两个语句有本质的区别，直接赋值直接创建有指定值的变量（也可能不会），但是第二条语句一定会先创建临时变量，然后赋值给a
// 临时变量：先存储在内存或别的指定位置，然后再复制到某位置
MyClass a = MyClass(1, 2); // 通常效率更高
a = MyClass(1, 2);
```

## STL

### Vector

一个关于方向处理的设计

``` cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    // 测试样例
    // 1
    // SSSSSLSSRS
    // 2
    // SR
    // SL
    int n;
    int x = 0, y = 0;
    cin >> n;

    vector<vector<int>> v = {{0, 1}, {1, 0}, {0, -1}, {-1, 0}};
    int d = 0;
    while (n--) {
        string str;
        cin >> str;
        for (int i = 0; i < str.size(); ++i) {
            if (str[i] == 'R') {
                d = d + 1;
                if (d > 3) {
                    d = d - 4;
                }
            } else if (str[i] == 'L') {
                d = d - 1;
                if (d < 0) {
                    d = d + 4;
                }
            } else if (str[i] == 'S') {
                x += v[d][0];
                y += v[d][1];
            }
        }
    }
    if (d != 0 || (x == 0 && y == 0)) {
        cout << "bounded" << endl;
    } else {
        cout << "unbounded" << endl;
    }
    return 0;
}
```

### Map

``` cpp
#include <map>

std:map<int, string> m;
m[1] = "One";  // 插入元素，如果元素是类对象，则开销比较大。我们可以用以下方法来避免开销
m.insert(map<int, string>::value_type(2, "Two"))

string tmp = m[2];  // 获取一个值的最简单方法，但是,只有当map中有这个键的实例时才对，否则会自动插入一个实例，值为初始化值

// 我们可以使用Find()和Count()方法来发现一个键是否存在。
std:map<int, string>::iterator it = m.find(1);
auto it2 = m.find(1);  // 更精简
if (it == m.end()) {
    // 没找到
}
// 通过map对象的方法获取的iterator数据类型是一个std::pair对象，包括两个数据 iterator->first 和 iterator->second 分别代表关键字和存储的数据

// iterator erase(iterator it); //通过一个条目对象删除
// iterator erase(iterator first, iterator last); //删除一个范围
// size_type erase(const Key& key); //通过关键字删除
// clear()就相当于 enumMap.erase(enumMap.begin(), enumMap.end());

// 遍历
for (auto it = m.begin();i t != m.end(); ++it) {
    cout << "key: " << it->first << " value: " << it->second <<endl;
}

// 错误使用erase, 如果某一个元素已经被删除，那么其对应的迭代器就失效了，不应该再被使用
for (auto it = m.begin(); it != m.end(); ++it) {
    m.erase(it);
}
// 正确使用
for (auto it = m.begin(); it != m.end();) {
  m.erase(it++); // 或者 it = m.erase(it);
}
```

## Algorithm

### Prime

``` cpp
bool is_prime[maxn];

int sieve(int n) {
    int p = 0;
    for(int i = 0; i <= n; ++i) {
        is_prime[i] = true;
    }
    is_prime[0] = is_prime[1] = false;
    for (int i = 2; i <= n; ++i){
        if(is_prime[i]){
            for(int j = i + i; j <= n; j += i) {
                is_prime[j] = false;
            }
        }
    }
    return 0;
}
```

### Fast Power

``` cpp
int fast_power (int b, int e) {
    int r = 1;
    while (e) {
        if (e & 1) {
            r *= b;
        }
        b *= b;
        b >>= 1;
    }
    return r;
}
```

### GCD

``` cpp
int gcd(int a, int b) {
    int t;
    while (b) {
        t = b;
        b = a % b;
        a = t;
    }
    return a;
}
```

### Union Find

``` cpp
union_find
```


### Sort

``` cpp
#include <iostream>
#include <algorithm>
#include <vector>

bool cmp (int i, int j) {
    return (i < j);
}

int main () {
    int arr[] = {32,71,12,45,26,80,53,33};
    std::vector<int> vec (arr, arr + 8);

    std::sort(vec.begin(), vec.begin() + 4);  // default <
    std::sort(vec.begin() + 4, vec.end(), cmp);

    for (std::vector<int>::iterator it = vec.begin(); it != vec.end(); ++it) {
        std::cout << ' ' << *it;
    }

    return 0;
}
```

## IO


### Multi Cin

``` cpp
#include <iostream>
using namespace std;
int main()
{
    // Sample Input
    // 1 5
    // 10 20
    // 400 516
    int a,b;
    while(cin >> a >> b)
    {
        cout << a+b << endl;
    }
    return 0;
}
```

### Getline()

``` cpp
#include <vector>
#include <sstream>

int main() {
    // istream& getline(istream& is, string& str, char delim);  从is开始读取字符, 直到遇到分隔符delim, 将读取的内容存入str
    // istream& getline(istream& is, string& str); 从is开始读取字符, 直到遇到换行符, 将读取的内容存入str
    string s;
    getline(cin, s);

    vector<string> stu;
    stringstream sstr(s);
    string token;

    while(getline(sstr, token, ',')) {
        stu.push_back(token);
    }
}
```

### split

stringstream可以吞下任何类型，根据实际需要吐出不同的类型。

``` cpp
int s2i(string s) {
    stringstream ss;
    ss << s;
    int x;
    ss >> x;
    return x;
}
```

``` cpp
string i2s(int i) {
    stringstream ss;
    ss << i;
    string s;
    ss >> s;
    return s;
}
```

``` cpp
void split(const string& s, vector<int>& v, const string& c) {
    string::size_type pos1, pos2;
    pos2 = s.find(c);
    pos1 = 0;
    while(string::npos != pos2) {
        v.push_back(stoi(s.substr(pos1, pos2-pos1)));
        pos1 = pos2 + c.size();
        pos2 = s.find(c, pos1);
    }
    if(pos1 != s.length())
    v.push_back(stoi(s.substr(pos1)));
}
```

```
#include <iostream>
#include <vector>
using namespace std;

void split(const string& s, vector<int>& v, const string& c) {
    string::size_type pos1, pos2;
    pos2 = s.find(c);
    pos1 = 0;
    while(string::npos != pos2) {
        v.push_back(stoi(s.substr(pos1, pos2-pos1)));
        pos1 = pos2 + c.size();
        pos2 = s.find(c, pos1);
    }
    if(pos1 != s.length())
        v.push_back(stoi(s.substr(pos1)));
}

int main() {
    string s;
    cin >> s;

    vector<int> v;
    split(s, v, ",");

    for (int i =0; i < v.size(); i++){
        cout << v[i] << endl;
    }
    return 0;
}
```

### CLIMIT

``` cpp
#include <climit>

INT_MIN
INT_MAX
LONG_MIN
LONG_MAX
LLONG_MIN
LLONG_MAX
```

