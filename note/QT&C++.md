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
## QT调整布局大小的方法
```
1 固定大小
QPushButton *button = new QPushButton("Button");
button->setSizePolicy(QSizePolicy::Fixed, QSizePolicy::Fixed);
2 最大最小尺寸
QPushButton *button = new QPushButton("Button");
button->setMinimumSize(100, 50); // 最小宽度100，高度50
button->setMaximumSize(200, 100); // 最大宽度200，高度100
3 增加间隔
QVBoxLayout *layout = new QVBoxLayout;
QPushButton *button = new QPushButton("Button");
layout->addWidget(button);
// 添加垂直间隔
layout->addStretch(1); // 这里的数字越大，间隔越大
4 手动设置xy坐标及大小
QPushButton *button = new QPushButton("Button");
button->setGeometry(50, 50, 100, 50); // x坐标50，y坐标50，宽度100，高度50
5 使用样式表
QPushButton *button = new QPushButton("Button");
button->setStyleSheet("QPushButton { min-width: 100px; max-width: 200px; min-height: 50px; max-height: 100px; }");
```
## QT找不到serial
```
sudo apt update
sudo apt install libqt5serialport5-dev
```
