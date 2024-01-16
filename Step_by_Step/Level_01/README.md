<h2>단계별로 풀어보기</h2>
<h3>[1단계] 입출력과 사칙연산</h3>

‼️ 오답 및 실수, 헷갈리는 개념 정리 <br><br>


|순번|문제 번호| 
|------|---|
|05|[1008번](https://www.acmicpc.net/problem/1008)|
|07|[10926번](https://www.acmicpc.net/problem/10926)|
|11|[11382번](https://www.acmicpc.net/problem/11382)|
|12|[10171번](https://www.acmicpc.net/problem/10171)|
|13|[10172번](https://www.acmicpc.net/problem/10172)|


<br>
<br>
<br>


<h4>[1008번]</h4><br>
문제에서 실제 정답과 출력값의 절대오차 또는 상대오차가 10^-9 이하이면 정답이라고 했다.<br>
여기서 쓸 수 있는 실수형 자료형은 크게 두 가지가 있다.<br>
<br>
float : 32비트(4바이트) 자료형<br>
double : 64비트(8바이트) 자료형<br>
<br>
오차를 줄이기 위해선 비트 크기가 더 큰 자료형을 써야하는데, 만약 float 자료형을 사용하면 틀렸다고 채점이 된다.<br>
float 자체로 해도 계산결과에는 오류가 없으나 소수 자릿수가 적게 나온다.<br>
<br>
float 자료형은 소수 7자리까지<br>
double 자료형은 소수 16자리까지 <br>
표현이 가능하다.<br>
<br>
즉, 이 문제에서는<br>
소수점을 9자릿수 이상 받을 수 있는 데이터 타입 지정과 소수점 고정이 핵심이다.<br>

자료형은 double 을 사용해야한다.<br>
double 로 지정하고<br>
```C++
cout << a / b;
```
해도 오답이라고 뜬다.<br>
=> double 이 소수점 이하 15자리(소수 16자리)까지 나타낸다고 해도<br>
출력은 그 이하로 되기 때문이다. <br>

=> '오차 범위'가 10^-9 이하여야 하기 때문에 출력 할 때에도 출력 할 소수점 자리를 9개 이상 출력하도록 해야한다. (= 소수점 고정) <br>

<br>
C++ 출력 방법<br>
cin, cout 사용 시 입력은 문제가 없지만 출력의 경우 약간 다르다. <br>
두 가지를 알아야 소수점 자리를 고정하여 출력 할 수 있다. <br>

첫 번째: fixed
fixed 는 고정 소수점 표기로, 만약 fixed를 쓰면 그 다음부터 틀어오는 출력들은 소수점 아래로 설정한 precision으로<br>
넘겨준 값 만큼 출력이 된다. <br>
아래와 같이 사용한다. <br>
```C++
cout << fixed;
```
<br>

두 번째 : cout.precision() / setprecision()<br>
precision() 은 출력할 실수 전체 자릿수를 n자리로 표현한 것이다.<br>
이때 주의할 점은 소수점 아래로 n 자리만큼 고정하는 것이 아니다. <br>
예를 들어 <br>
```C++
double a = 1234.5678;
std::cout.precision(6);
 
std::cout << a;	// 1234.567 에서 반올림 된 1234.57 이 출력 됨
```
<br>
따라서 오차범위를 넉넉하게 주려면 precision의 파라미터를 큰 수로 넘겨주어야 한다. <br>
precision()은 헤더파일을 추가했을 때와 하지 않았을 때의 표기법이 다르다. <br>

1. <iomanip> 헤더파일 추가할 경우<br>
   cout << setprecision(n);
<br>
2. 추가하지 않을 경우<br>
   cout.precision(n);

<br>
<br>
<최종 코드> <br>
 ```C++ 
#include <iostream>

using namespace std;

int main()
{
    double a, b;
    
    cin >> a >> b;
    
    cout << fixed; // 소수점 고정 
    cout.precision(9); // 9자리까지 표현
    
    cout << a / b << endl;
    
    return 0;
}
```





