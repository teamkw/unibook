### 간단하게 c++로 Hello World 출력하기

``` c++
#include <iostream>

int main(Void) {
    cout << "Hello World!";
    return 0;
}
```
c++에는 stdio.h와 비슷하게 iostream헤더가 입출력 해더와 다른 함수들을 가지고 있습니다. printf와 비슷한 것은 cout이며 이외에는 c에서 배운 것과 같습니다

이를 컴파일 해봅시다

g++ hello.cpp -o hello.out

c++의 확장자는 cpp이므로 이를 사용해주고 c++이므로 g++을 통하여 컴파일을 할 수 있습니다!!

__c와 c++ 언어에서의 Hello World를 출력하는 방법에 대해서 알아보았으며 이제 다음챕터로 넘어가봅시다!!__