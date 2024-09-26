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
## QT信号与槽四种表达方式
```
QObject::connect(sender, &Sender::signalName, receiver, &Receiver::slotName); //普通直连
QObject::connect(sender, SIGNAL(signalName()), receiver, SLOT(slotName())); //字符串
QObject::connect(sender, QOverload<int>::of(&Sender::signalName), receiver, &Receiver::slotName); //信号重载
QObject::connect(sender, &Sender::signalName, [=]() { receiver->slotName(); }); //lambda表达式
```
