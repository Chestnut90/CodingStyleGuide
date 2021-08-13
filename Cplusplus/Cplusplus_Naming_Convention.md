# Naming Convention

<br/>

### File Naming & Define

1. **Pascal Case**를 통해서 파일명을 작성하며, [filename].h 와 [filename].cpp는 동일 이름의 쌍으로 존재한다.
2. \<filename>.h 파일에서 일부 공통 항목을 다른 \<filename>.cpp에 작성하는 경우 \<filename>.\<module>.cpp로 분할 할 수 있다.
   - 중첩 클래스 정의
   - 함수 집합의 다양성
3. Header 파일의 전처리기는 \_\<PROJECT>\_\<SUPER>\_\<FILENAME>\_H_ 형식으로 작성한다.
   - PROJECT : 해당 프로젝트 명
   - SUPER : 상위 집합 이름 또는 영역
   - FILENAME : 해당 클래스 혹은 파일의 이름

  ```c++
  // file path
  // SDK (project)
  //  - Shape (directory)
  //		- Rectangle.h
  //		- Rectangle.cpp
  //		- Rectangle.Point.cpp	// 중첩 클래스 정의
  //		- Rectangle.IO.cpp		// I/O 관련 함수 집합
  
  #ifndef _SDK_SHAPE_RECTANGLE_H_
  #define _SDK_SHAPE_RECTANGLE_H_
  namespace SDK::Shape
  {
      class Rectangle
      {
          class Point	// 중첩 클래스 (nested class)
          {
              // ...
          }
          //	...
  
      public:
          void DoSomethingAboutIO();
          // ...
      }
  }
  #endif //!_SDK_SHAPE_RECTANGLE_H_
  
  ```

<br/>

