# 🚀 C++ Quick Reference & Examples

## 🔹 1. Input / Output (`<iostream>`, `<string>`)
```cpp
cin >> var;              // Input
cout << var;             // Output
getline(cin, str);       // Full line input
cin.ignore();            // Clear buffer
tie(nullptr);            // Untie streams for faster I/O
```
## 🔹 2. Math (<cmath>)
```cpp
abs(x); sqrt(x); pow(x, y);
ceil(x); floor(x); round(x);
fmax(a, b); fmin(a, b);
hypot(x, y);
sin(x); cos(x); tan(x);
asin(x); acos(x); atan(x);
log(x); log10(x); exp(x);
```
## 3. Utilities (<algorithm>, <utility>, <numeric>)
```cpp
min(a, b); max(a, b);
swap(a, b);
sort(begin, end);                   // Ascending
sort(begin, end, greater<>());      // Descending
reverse(begin, end);
count(begin, end, val);
find(begin, end, val);
binary_search(begin, end, val);
lower_bound(begin, end, val);
upper_bound(begin, end, val);
accumulate(begin, end, init);
gcd(a, b); lcm(a, b);               // Since C++17
fill(begin, end, val);
iota(begin, end, start);
```
## 4. String (<string>)
```cpp
s.size(); s.empty();
s.substr(pos, len);
s.find(str); s.rfind(str);
s.append(str); s += str;
s.push_back(ch); s.pop_back();
s.insert(pos, str);
s.erase(pos, len);
s.compare(str);
stoi(str); stol(str); stoll(str);
stof(str); stod(str); stold(str);
to_string(num);
```
## 5. Vector (<vector>)
```cpp
v.size(); v.empty();
v.push_back(x); v.pop_back();
v.front(); v.back();
v.clear();
v.insert(pos, val);
v.erase(pos);
sort(v.begin(), v.end());
reverse(v.begin(), v.end());
find(v.begin(), v.end(), x);
```
## 6. Set / Map (<set>, <map>, <unordered_set>, <unordered_map>)
```cpp
insert(x); 
erase(x);
count(x);
find(x);
size();
clear();
lower_bound(x);
upper_bound(x);
```
## 7. Queue / Stack (<queue>, <stack>, <deque>)
```cpp
q.push(x);
q.pop();
q.front();
q.back();
s.top();
empty();
size();
```
## 8. Priority Queue (<queue>)
```cpp
priority_queue<int> pq;                                 // Max heap
priority_queue<int, vector<int>, greater<int>> pq;      // Min heap
pq.push(x);
pq.pop();
pq.top();
```
## 9. Time (<chrono>, <ctime>)
```cpp
time(0);
ctime(&t);
clock();
chrono::high_resolution_clock::now();
```
## 10. File I/O (<fstream>)
```cpp
ifstream fin("file.txt");
ofstream fout("file.txt");
getline(fin, str);
fin.close(); fout.close();
```
## Function Template
```cpp
template <typename T>
T add(T a, T b) {
    return a + b;
}

int main() {
    cout << add(10, 20) << endl;      // int version
    cout << add(5.5, 4.4) << endl;    // double version
    cout << add('A', 1) << endl;      // char + int version
}
```

## Class Template
```cpp
template <class T>
class Box {
    T value;
public:
    Box(T v) : value(v) {}
    T getValue() { return value; }
};

int main() {
    Box<int> intBox(123);
    Box<string> strBox("Hello Templates");

    cout << intBox.getValue() << endl;
    cout << strBox.getValue() << endl;
}
```
## Example: goto
```cpp
#include <iostream>
using namespace std;

int main() {
    int num = 1;

start:
    cout << num << " ";
    num++;

    if (num <= 5)
        goto start;

    return 0;
}
```
## Lambda Expressions
```cpp
//Syntax
/*
[capture_list] (parameters) -> return_type {
    // function body
};
*/

//Example 1: Basic Lambda
auto greet = []() {
    cout << "Hello, Lambda!" << endl;
};
greet();


//Example 2: With Parameters
auto add = [](int a, int b) { return a + b; };
cout << add(10, 20);

//Example 3: Capture by Value
int x = 5, y = 10;
auto sum = [x, y]() { return x + y; };
cout << sum();


//Example 4: Capture by Reference
int counter = 0;
auto increment = [&counter]() { counter++; };
increment(); increment();
cout << counter;


//Example 5: Generic Lambda (C++14+)
auto multiply = [](auto a, auto b) { return a * b; };
cout << multiply(3, 4);
cout << multiply(2.5, 4.2);


//Example 6: Full Syntax Example
int a = 10, b = 20;
auto myLambda = [a, &b](int x, int y) -> int {
    cout << "Inside lambda: a = " << a << ", b = " << b << endl;
    b += 5;
    return a + b + x + y;
};
int result = myLambda(5, 15);
cout << "Result = " << result << endl;
cout << "After lambda call, b = " << b << endl;
```
## Try-Catch Block
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cin >> n;

    try {
        if (n == 0)
            throw runtime_error("Division by zero is not allowed");

        cout << 10 / n << endl;
    }
    catch (const exception &e) {
        cout << "This is invalid bro: " << e.what() << endl;
    }
}
```
