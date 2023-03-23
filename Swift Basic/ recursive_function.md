## 재귀함수
+ 자신을 반복해서 호출하는 함수이다.
+ 변수를 여러개 선언할 필요가 없고, 반복문을 사용하지 않아도 되기에 코드가 간결해지는 장점이 있다.
+ 조건을 제대로 설정하지 않는다면 무한으로 스택프레임이 쌓여서 '스택오버플로우'가 일어날 수 있으므로 주의
~~~swift
func factorial(num: Int) -> Int {
    if num <= 1 {
        return 1
    }
    return num * factorial(num: num - 1)
}
~~~