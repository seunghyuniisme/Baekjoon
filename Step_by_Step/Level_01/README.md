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
결론은 자료형으로 double 을 사용해야 맞게 채점이 된다.<br>
<br><br>
***

