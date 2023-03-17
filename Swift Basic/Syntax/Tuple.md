## 튜플
+ 2개 이상의 연관된 데이터를 조합하여 사용하기 위한 타입

**사용하는 이유: 함수는 원칙적으로 리턴값이 1개. 여러 개의 값을 리턴할 수 없으므로 튜플을 이용해 묶음으로 리턴**
~~~swift
var oneTwo: (Int, Int) = (1, 2)

var oneTwoThree = (1, 2, 3)
~~~
+ 내부의 데이터에 각각 접근하는 방법
~~~swift
oneTwoThree.0 // 1 
oneTwoThree.1 // 2
oneTwoThree.2 // 3
~~~
+ Named Tuple : 사용 시 코드 가독성이 높아짐
~~~swift
var man = (age: 20, name: "홍길동")

man.age //20
man.name // 홍길동
~~~
+ 분해 : 한 개씩 분해해서 상수나 변수에 저장이 가능함
~~~swift
var (a, b, c) = oneTwoThree
a // 1
b // 2
c // 3
~~~
+ 다른 튜플끼리 값 비교 가능함 (실제로 사용되는 경우는 드물다)
~~~swift
(2, "banana") < (3, "apple")   // true
(3, "apple") < (3, "banana")   // true
(9, "cat") == (9, "cat")    // true
~~~
    1) 첫번째 요소끼리 비교가 먼저임. 여기서 조건이 일치하면 true
    2) 첫번째가 서로 일치한다면 2번째로.

## switch문에서의 튜플
+ 스위치문은 튜플 매칭을 지원한다.
~~~swift
switch iOS {
case ("Swift", "5"):
    print("버전 5입니다.")
case ("Swift", "4"):
    print("버전 4입니다.")
default:
    break
}
~~~
+ 바인딩도 가능하다.
~~~swift
var cd = (12, 0)
// (0, 7)과 (4,6)의 경우에는 어떤 결과가 나올지 생각

switch cd {
case (let x, 0), (0, let x):
    print("x축 또는 y축 위에 위치, \(x)만큼 거리가 떨어져 있다.")
default:
    print("x축이나 y축 위에 있지 않음")    
} 
~~~

    x축 또는 y축 위에 위치, 12만큼 거리가 떨어져 있다.

+ 튜플의 where활용
~~~swift
switch number {
    let(x, y) where x == y:
    print("same")
default
    break
}
~~~

