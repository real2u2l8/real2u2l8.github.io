---
layout: post
title: "[basically]C/C++ 알고 가야 할 것"
subtitle: C와 C++의 차이점 그리고 몇가지의 특성들
categories: C/C++
tags: [C/C++]
published: true
---
## 1. C/C++각각의 차이

---

## 무엇이 다를까?

---

```cpp
int main(){
 //C
 printf("~~~\n");
 //C++
 std::cout << "~~~" << std::endl;
 return 0;
}
```

### C

- 직접적인 작성자, 라이브러리 작성자는 본인이 사용할 함수(기능)을 직접적으로 구현해야한다.
- 어떠한 함수를 사용하려면 그 함수에 대해서 잘 알아야한다. (printf()의 원형과 정의를 잘 알아야한다.)

### C++

- EX) 리다이렉트 (<< , >>)와 같은 문자를 이용해 어떠한 기능(객체 사용)을 즉각적으로 사용할 수 있게 된다.
- 즉, 내가 어떠한 함수, 객체를 완벽하게 알 필요가 없다. (세탁소 아저씨에게 세탁을 맡기는 느낌)

> **C와 C++의 차이는 구조가 간결해 진다.**
>

## 2. 인스턴스(Instant, 사실, 구현)?

---

C언어에서 자료형 변수; 형태로 사용하게 되는데 쉽게 설명하면 변수를 인스턴스로 부르게 된다.

## 3. Namespace, cout, cin

---

### Namespace (’std::cout’ 에서 std)

- 의역하자면 ‘소속, 가문’이라고 번역해보자
- C언어에서는 소속에 개념이 없다
- 분류한다. 묶음으로 엮어준다.

### cout

- Console out?
- 콘솔 출력
- cout << 값
- printf 처럼 형식 문자를 입력하지 않아도 알아서 출력한다
  - 사용자가 기대한 출력이 나오지 않을 수도 있다 말 그대로 **알아서** 이기 때문

### cin

- Console in?
- 콘솔 입력 (키보드 입력)
- cin >> 인스턴스

## 4. 자료형

---

### auto

- 데이터 형의 자동화

### 변수 선언과  선언 및 정의

- int a = 10; //C언어 식 정의 및 정의
- **int b(10); //C++식 선언 및 정의**

```cpp
int main(){
 int a(10); //
 int b(a); // b를 출력하면 10이 나옴, 복사의 의미가 된다. 
 int (10); // 이행위도 된다. -> 변수가없는데도 된다. -> 상수처리 됨. 이름이 없는 인스턴스
 
 auto b(a); //auto의 의미는 a의 자료형을 따라가게 된다.
 return 0;
}
```

- auto는 정말 위대하다
- 한번정도 자료형을 선언해 주면 알아서 만들어 준다.
- C언어에서 함수 포인터 사용에 대한 귀찮은 문제를 auto 하나로 쉽게 사용가능하다.

```cpp
#include <iostream>

void funcWithAuto(int, char *){}

int main(){
  void(*pfFunc)(int, char*) = funcWithAuto;

  auto pfFunc2(funcWithAuto);

  return 0;
}
```
