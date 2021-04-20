## Introduction

- templating works like macros and substitute the code during compile time, but also does type checking

- typename and class can be interchangeable
```c++
template <typename T>
template <class T>
```

#### template variable
    Available from C++ 14
```c++
template <typename T>
T pi = T(3.1415926535897932385L);

template <typename T>
T areaCircle(const T &r)
{
    return (r * r * pi<T>);
}

int main()
{
    std::cout.precision(20);
    std::cout << pi<long double> << "\n";
    std::cout << areaCircle<long double>(4) << "\n";
    std::cout << areaCircle<double>(4) << "\n"; // Will give correct output to 16 places only
}
```