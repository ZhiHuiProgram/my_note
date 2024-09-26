# My QT C++

## C++使用lambda表达式对成员函数的捕获（函数指针）
```
#include <iostream>

class MyClass {
public:
    void myFunction(int value) {
        std::cout << "Called MyClass::myFunction with value: " << value << std::endl;
    }
};

int main() {
    MyClass obj;

    // 使用lambda表达式来捕获成员函数
    auto funcPtr = [&obj](int value) { obj.myFunction(value); };

    // 调用成员函数
    funcPtr(42);

    return 0;
}
```
