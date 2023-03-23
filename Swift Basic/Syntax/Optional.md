# 옵셔널 타입
    기본적으로 타입이란, 해당 메모리 공간의 값에 대한 정보이다.
    (선언만 되어있는) 빈 메모리 공간에 접근하게 되면 오류가 발생하므로,
    이러한 상황이 일어나도 앱이 종료되는 등의 일을 막기 위해 도입한 것이 '옵셔널 타입'


## 기본 특징
+ 기존 타입 뒤에 ?를 붙이면 옵셔널 타입이 된다.
~~~swift
var num: Int? = 26
~~~
+ 값이 없음을 나타내는 키워드로 'nil'을 사용한다.
~~~swift
var num: Int? = nil
~~~

+ 값을 대입하지 않으면 nil로 자동 초기화된다.
~~~swift
var num1: Int?

print(num1)
~~~
    nil 

+ nil만으로는 타입 추론이 불가능하다. 어떠한 옵셔널 타입인지 컴파일러가 알 수 없기 때문이다.
* 정식 문법의 형태 참고. '옵셔널 타입'이 아닌 '옵셔널 정수형', '옵셔널 문자열', ...
~~~swift
var num1 = nil // (x)    
var num2: Int? = nil // (o)


var num3: Optional<Int> // Int + nil
~~~
+ 옵셔널 타입간 연산은 불가능하다.

## 추출 방법

### 1. 강제 추출
+ 확실하게 값이 있을때만 사용
~~~swift
name!
~~~
### 2. if문
+ 조건을 통해 nil이 아닐경우 강제 추출 
~~~swift
if name != nil {
    print(name!)
}
~~~
### 3. **옵셔널 바인딩**
+ 대부분의 경우에 이 방법을 사용할 것을 권장
+ 추출한 값이 상수에 바인딩된다면 특정 작업을 실행한다.
+ 추출된 값이 타입 추론을 통해 바인딩 된다 == nil이 아니다
~~~swift
if let x = name {
    print(x)
}
~~~
+ 앱 제작시에는 guard let을 많이 사용한다.
~~~swift
func doSometing(name: String?) {
    guard let n = name else { return }
    print(n)
}
~~~
### 4. 닐 코얼레싱 (Nil-Coalescing) 연산자
+ 기본값을 제시
+ 값이 있다면 추출해서 사용하고, nil이라면 제시한 기본값을 사용하겠다.
~~~swift
var name: String? = "홍길동" 
var str: String?

print(name ?? "미인증사용자")
print(str ?? "Guten Tag!")
~~~
    홍길동
    Guten Tag!