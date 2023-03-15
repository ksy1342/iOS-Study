## 조건문 if
조건의 자리에 값을 참 또는 거짓으로 가지는 표현식을 사용
~~~swift
if age >= 18 {
    print("성인입니다.")
}
~~~


### 1. if - else
~~~swift
if age >= 18 {
    print("성인입니다.")
 } else {
    print("미성년자입니다.")
 }
~~~
### 2. else if
else if를 사용할 때는 순서가 중요하다.
~~~swift
var score = 95

if score >=90 {
    print("A")
} else if score >=70 {
    print("B")
} else {
    print("C")
}
~~~
    A
~~~swift
var score = 95

if score >= 70 {
    print("B")
} else if score >=90 {
    print("A")
} else {
    print("C")
}
~~~
    B

*즉, 범위가 작은 조건이 앞에 와야 한다.*



### 3. 중첩 if문
~~~swift
if number > 0{
    if number % 2 == 0 {
        print("양의 짝수입니다.")
    } else {
        print("양의 홀수입니다.")
    }
} else {
    if number % 2 == 0 {
        print("음의 짝수입니다.")
    } else {
        print("음의 홀수입니다.")
    }
}
~~~


## Switch문
if문 보다 한정적인 상황에서 사용. 
> 부등식 (x) , == (o)

즉, 변수가 어떤 값을 가지느냐에 따라 다른 결과를 실행하고자 할 때 사용한다.
### 1. 특징
+ 각 케이스에는 ,를 사용해 다수의 매칭값을 넣을 수 있다.
~~~swift
switch str {
case "a","b":
    print("a or b")
}
~~~
+ 각 케이스에는 문장이 최소한 하나는 있어야 한다. 실행하지 않고 넘어가려면 break를 사용해야 한다.
~~~swift
switch str{
case "a":
    print("a")
case "b":
    break
}
~~~
+ 변수와 비교 가능한 모든 경우의 수가 필요하다. else와 유사한? default 케이스를 사용한다.
~~~swift
switch str{
case "a":
    print("a")
default:
    break
}
~~~
 *변수의 값이 참/거짓인 경우 비교할 경우의 수가 2가지 밖에 없으므로 default 케이스가 필요없다.*

### 2. fallthrough
+ 변수와의 매칭을 고려하지 않고 무조건 다음 케이스의 문장을 실행한다.
~~~swift
var number = 5

switch number {
case ..<7:
    print("5")
    fallthrough
case 100:
    print("100")
    fallthrough
default:
    print("30")
}
~~~
    5
    100
    30

[fallthrough사용시 유의점](https://github.com/ksy1342/iOS-Study/blob/main/Swift%20Basic/fallthrough.md)

### 3. 범위 매칭
+ 스위치문은 기본적으로 부등식을 사용할 수 없지만, 범위연산자와 패턴 매칭 연산자를 통해 범위 매칭을 지원한다.
~~~swift
//내부적으로 ==, ~= 을 지원
switch number {
case ..< 0:
    print("0 미만")
case 0...99:
    print("0 ~ 99")
case 100...:
    print("100 이상")
default:
    break
}
~~~

### 4. 바인딩
*바인딩? 기존의 변수나 상수를 복사하여 새로운 식별자로 할당하는 것*
~~~swift
var num = 27

switch num {
case let n:
    print("정수: \(n)")
default:
    break
}
~~~
+ 상수 바인딩이 기본 (-> 바인딩한 값을 내부에서 초기화 해야 할때만 변수로 바인딩)
+ 바인딩 된 상수는 해당 케이스 내에서만 사용 가능하다.
+ 주로 조건을 확인하는 where와 같이 사용된다. 
~~~swift
var num = 10

switch num {
case let a where a % 2 == 0:
    print("짝수: \(a)")
case let a where a % 2 != 0:
    print("홀수: \(a)")
default:
    break
}
~~~
