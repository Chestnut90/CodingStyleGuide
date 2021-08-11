# Naming Convention

<br/>

### File Naming

- Pascal Case를 통해서 파일명을 작성하며, [filename].h 와 [filename].cpp는 동일 이름의 쌍으로 존재한다.

  ```
  # Rectangle.h 
  # Rectangle.cpp
  ```

- [filename].h 파일에서 일부 공통 항목을 다른 [filename].cpp에 작성하는 경우 [filename].[module].cpp로 분할 할 수 있다.

  ```
  class Rectangle
  {
  	class Point
  	{
  	}
  }
  
  # Rectangle.h
  # Rectangle.cpp
  # Rectangle.Point.cpp // Point는 Rectangle의 하위 클래스
  ```

<br/>

### File Define

- header 파일의 전처리기는 \_[PROJECT]\_[SUPER]\_[FILENAME]\_H_

  ```
  // file path
  // SDK (project)
  //  - Shape (directory)
  //		- Rectangle.h
  
  #ifndef _SDK_SHAPE_RECTANGLE_H_
  #define _SDK_SHAPE_RECTANGLE_H_
  class Rectangle
  {
  	...
  }
  #endif //!_SDK_SHAPE_RECTANGLE_H_
  ```

<br/>

