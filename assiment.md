```cpp
#include <iostream>
using namespace std;

class Time {
private:
    int hours;
    int minutes;
    int seconds;

public:
    Time() : hours(0), minutes(0), seconds(0) {}
    Time(int h, int m, int s) : hours(h), minutes(m), seconds(s) {}
    ~Time() {
        cout << "Time object deleted" << endl;
    }

    void displayTime() const {
        cout << hours << ":" << minutes << ":" << seconds << endl;
    }

    // Copy constructor
    Time(const Time &other) : hours(other.hours), minutes(other.minutes), seconds(other.seconds) {}
};

int main() {
    Time t1;
    Time t2(10, 30, 45);
    Time t3(t2); // Corrected copy constructor call
    cout << "Time t1: ";
    t1.displayTime();
    cout << "Time t2: ";
    t2.displayTime();
    cout << "Time t3: ";
    t3.displayTime();
    return 0;
}
