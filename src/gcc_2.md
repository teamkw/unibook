### gcc에 대한 기본 이해

gcc를 소스를 가져다 손수 설치해보신 적은 없을 것입니다. 보통은 바이너리 패키지로 된 것을 가져다 설치를해요! gcc 패키지가 어떤 것으로 구성되어있는지! gcc가 제대로 설치되어 있는지 알보봅시다

/lib/cpp      ----> /usr/lib/gcc-lib/i386-linux/2.7.2.1/cpp (링크)   
/usr/bin/cc   ----> gcc (링크)   
/usr/bin/gcc             C 컴파일러 'front-end'   
/usr/bin/protoize   
/usr/bin/unprotoize   
/usr/info/cpp.info->.gz  GNU info 시스템을 이용하는 파일들   
/usr/info/gcc.info->.gz   
/usr/lib/gcc-lib   

마지막 /usr/lib/gcc-lib 디렉토리에 gcc에 관한 모든 내용이 설치됩니다.

보통은 이러한 형식으로 디렉토리 구조를 가집니다.   
/usr/lib/gcc-lib/<플랫폼>/<gcc 버전>

/usr/lib/gcc-lib 밑의 내용을 살펴보겠습니다

/usr/lib/gcc-lib/i386-linux/2.7.2.1/cc1   
/usr/lib/gcc-lib/i386-linux/2.7.2.1/cpp   
/usr/lib/gcc-lib/i386-linux/2.7.2.1/include/*.h   
/usr/lib/gcc-lib/i386-linux/2.7.2.1/libgcc.a   
/usr/lib/gcc-lib/i386-linux/2.7.2.1/specs   

cc1은 진짜 C 컴파일러 본체입니다. gcc는 단지 적절하게 C인지 c++인지 아니면 오트젝티브 C 인지를 검사하며 컴파일 작업만 아니라 __"링크"__ 라는 작업까지 C 언어로 프로그램 소스를 만든 다음, 프로그램 바이너리가 만들어지기까지의 모든 과정을 관장해주는 "조정자"역할을 해줍니다.

C 컴파일러는 cc1, C++ 컴파일러는 cc1plus, 오브젝티브 C 컴파일러는 cc1obj입니다. 여러분이 C++/오브젝티브 C 컴파일러를 설치하셨다면 cc1plus, cc1obj 라는 실행파일도 찾아볼 수 있습니다. cpp는 "프리프로세서"입니다. #include 등의 본격적인 cc1 컴파일에 들어가기에 앞서 먼저(pre) 처리(process)해주는 녀석입니다.

g++ 즉 C++ 컴파일러에 대한 패키지는 다음과 같습니다.
/usr/bin/c++ ---------------------------------> (링크)   
/usr/bin/g++   
/usr/bin/gcc-lib/i386-linux/2.7.2.1/cc1plus     (진짜 C++ 컴파일러)   

오브젝티브 C 컴파일러 패키지는 다음과 같습니다.

/usr/lib/gcc-lib/i386-linux/2.7.2.1/cc1obj   
/usr/lib/gcc-lib/i386-linux/2.7.2.1/include/objc/*.h   
/usr/lib/gcc-lib/i386-linux/2.7.2.1/libobjc.a   