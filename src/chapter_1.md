# Chapter 1



| nom | acc  | dat   |
| --- | ---- | ----- |
| ich | mich | mir   |
| du  | dich | dir   |
| Sie | Sie  | Ihnen |
| er  | ihn  | ihm   |
| sie | sie  | ihr   |
| es  | es   | ihm   |
| wir | uns  | uns   |
| ihr | euch | euch  |
| Sie | Sie  | Ihnen |
| sie | sie  | ihnen |



```cpp
#include "Grid.h"
#include <print>

class Myclass {
    public:
        int getM() const;
        void setM(int m);
    private:
        int m_m {0};
};

int Myclass::getM () const {
    return m_m;
}

void Myclass::setM(int m) {
    m_m = m;
    return;
}

int main () {
    Grid<int> myIntGrid;
    Grid<double> myDoubleGrid {11, 11 };

    myIntGrid.at(0,0) = 10;

    int x {myIntGrid.at(0,0).value_or(9)};
Grid<int> grid2 {myIntGrid};
Grid <int> anotherIntGrid;
anotherIntGrid = grid2;
Grid<Myclass> mc;
Myclass mp;
mc.at(2,2) = mp;
mc.at(2,2)->setM(18);
std::println("mc.at(2,2).getM() is {}", mc.at(2,2)->getM());
}
```