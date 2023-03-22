+ 항상 정의, 실행의 2단계로 이루어진다.

## 형태
### 1. input이 있는 함수
+ 소괄호 내부에 파라미터의 이름과 타입을 입력
~~~swift
func hi(name: String) {
    print("안녕하세요, \(name)님")
}

hi(name: "홍길동") // "홍길동" : 아규먼트
~~~
    안녕하세요, 홍길동님

### 2. output이 있는 함수
+ 함수() -> 리턴값의 타입
~~~swift
func hello() -> String {
    return "안녕하세요."
} 

print(hello())
~~~
    안녕하세요.
### 3. 기타
+ 아웃풋이 없는 함수는 리턴값의 타입부분에 'Void'를 입력
+ 편의상 생략하여 2의 형태로 입력
+ 참고만. 아웃풋이 없는 형태의 함수는 거의 사용되지 않음
~~~swift
//1
func  hi() -> Void {
    print("hi")
}

//2

func  hi() {
    print("hi")
}
~~~

## 응용
### 1. 아규먼트 레이블
+ 파리미터의 이름을 정할 때, 별칭을 이용하는 것
+ 함수 작성 시 내부에서는 a, b 처럼 단순하게 사용   
+ 아규먼트를 받을 때는 별칭을 통해 함수가 값으로 무엇을 원하는지 자세하게 파악가능
~~~swift
func insert1(firstName a: String, lastName b: String) {
    ...
}

insert1(fistName: "길동" , lastName: "홍")

~~~

+ 와일드카드 패턴으로 이름 생략도 가능
~~~swift
func plus(_ first: Int, _ second: Int) {
    print(first + second)
}

plus(3, 7)
~~~
    10

### 2. 가변 파라미터
+ 타입...
+ 여러 개의 아규먼트를 전달할 수 있으며, 배열형태로 전달
+ 기본값을 가질 수 없음
~~~swift
func average(_ numbers: Double...) -> Double {
    var total = 0.0
    for i in numbers {
        total += i
    }
    return total / Double(numbers.count)
}

print(average(1, 2, 4, 6))
~~~
    3.25

### 3. 파라미터의 기본값
+ 파라미터도 기본값 설정 가능
+ 파라미터들의 기본값을 정해놓고, 일부만 아규먼트를 입력받게 
+ 스위프트의 기본 함수들중 이 형태가 많음. 프린트 함수가 대표적 예시

        print(items: Any...)


## 주의점
### 1. 파라미터는 상수
+ 받은 값을 수정하고 싶을 경우 새로운 변수 선언이 필요
~~~swift
func plusN (_ num1: Int, _ num2: Int) {
    // num1 = num1 + 3 (x)
    var num3 = num1 + 3
    ...
}
~~~

### 2. 리턴타입의 유무
+ 'return'의 사용법이 달라짐
+ 리턴타입이 있으면, 리턴값을 의미함
~~~swift
func hi() -> String {
    return "hi"
}
~~~
+ 리턴타입이 없으면, 함수의 종료를 의미함
~~~swift
func number(_ num: Int) {
    if num > 0 {
        print("양의 정수입니다.")
        return
    }
    print("음의 정수입니다.")
}
~~~

### 3. 함수의 중첩
+ 함수 내부의 변수처럼, 당연히 외부에서 사용 불가능

## 함수 표기법
+ 함수를 지칭하려는 경우 (변수에 함수를 담는 등)
        
        기준 : function()

1. 파라미터가 없는 경우
    
    : ( ) 삭제
    
        function

2. 아규먼트 레이블이 있는 경우 

    : 아규먼트 레이블까지를 풀네임으로 봄

        function(number:)
        
        function(_:)

3. 파라미터가 여러개인 경우 

    : 콤마없이 붙여서 표기
        
        function(a:b:)

4. 함수 타입
+ 변수에 담을 때 함수의 타입을 명시할 수 있다.
+ 즉, 함수도 특별한 형태의 타입을 가짐.
~~~swift
var num: (String) -> void = number(n:)
~~~


## 오버로딩
+ 하나의 함수 이름에 여러 개의 함수를 대응
+ 동일한 기능을 수행하지만 파라미터의 타입이 다양할 경우, 여러개를 쓰지않고 편하게.
+ 컴파일러는 타입, 아규먼트 레이블, 리턴값 등으로 구별함
~~~swift
func doSomething(value: Int) {
    print(value)
}

func doSomething(value: Double) {
    print(value)
}

func doSomething(value: String) {
    print(value)
}
~~~ 
