# C++ Coding Style Guide

<br/>

## References

- [**isocpp**](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#S-introduction)
- [**Google C++ Style Guide**](https://google.github.io/styleguide/cppguide.html)

<br/>

## Contents

1. [**Naming Rules**](#Naming Rules)
    - [**File**](#File Naming)
    - [**Namespace**](#Namespace)
    - [**Variable**](#Variable Naming)
    - [**Type**](#Type Naming)
    - [**Function**](#Function Naming)
2. [**Class**](#Class)
3. [**Struct**](#Struct)

<br/>

## Naming Rules

- 가독성, 개발 유지 보수를 위한 명명 방식을 규정하고 사용한다.

<br/>

### File Naming
- *.h와 *.cpp 파일을 쌍으로 관리한다.
    - 파일명은 Pascal case로 작성한다.
    - struct, enum 등 선언과 정의가 동시 필요한 참조의 경우 *.h만 작성한다.
    - 중첩 클래스, 함수 집합의 경우 \<FILE_NAME>.\<MODULE NAME>.cpp를 통해 분리한다.
- 파일 선언은 \_\<PROJECT>\_\<FILE_NAME>\_H\_ 형식으로 중복을 피한다.
    - 선언은 언더바('_', under score)와 대문자(upper case)로 작성한다.
```c++
// file path
// SDK (project)
//  - Shape (directory)
//		- Rectangle.h
//		- Rectangle.cpp
//		- Rectangle.Point.cpp	// *중첩 클래스 정의
//		- Rectangle.IO.cpp		// *I/O 관련 함수 집합

#ifndef _SDK_RECTANGLE_H_	// *file define
#define _SDK_RECTANGLE_H_ // *file define
namespace SDK::Shape
{
    class Rectangle
    {
        class Point	// *중첩 클래스 (nested class)
        {
            // ...
        }
        //	...

        // *I/O functions
    public:
        void Open();
        // ...
        void Save();
    }
}
#endif //!_SDK_RECTANGLE_H_ // *file define
```
<br/>
### Namespace
- namespace의 유용성.
    - 모듈 집합을 나타낼 수 있다.
    - 모듈간 선언 및 정의의 출동을 피할 수 있다.
``` c++
// above c++ 17 version
namespace SDK::Shapes	// set of shapes
{
    class Rectangle;
    class Ellipse;
    class Triangle;
}

// under c++ 17 version
namespace SDK
{
    namespace Shapes
    {
        class Rectangle;
    }
}
```
<br/>
### Variable Naming
- 언더바('_', under score)와 소문자(lower case)를 이용하여 변수를 선언한다.
- 변수 이름을 통해서 충분한 의미를 파악할 수 있도록 명명한다.
- 타입을 나타내기 위한 접두사 혹은 접미사를 붙이지 않는다.
- boolean type의 경우 is, on, has 등 전치사를 통해 의미를 부여한다.
```c++
int count;
int n_count; // BAD

bool is_done;		
bool on_running;	// running state
```
<br/>
### Type Naming
- 클래스(**class**), 구조체(**struct**)는 **pascal case**를 통해 명명한다.
- 상수(**constant value**)는 'k' 접두사와 함께 **pascal case**를 사용한다.
    - 'k'는 일반적으로 상수를 나타내는 문자.
- 함수(**function**)는 **pascal case**를 사용하며, 함수 역할을 충분히 나타낼 수 있도록 작성한다.
- 열거자(**enum**)는 enum class를 통해 선언하며, **pascal case**를 통해 선언
<br/>
### Function Naming
<br/>
## Class
## Struct