## 변수 var,  상수 let

변수나 상수의 선언 → 메모리 공간을 생성
~~~swift
//문자열 내부에서 사용방법
var name = "홍길동"

print("제 이름은 \(name)입니다")
~~~


## 타입 주석(Type Annotation)
스위프트에서 변수와 상수는 '타입 주석'을 통해 해당 저장 공간에 어떤 타입의 값이 들어있는지, 혹은 어떤 타입의 값이 들어가야 하는지를 컴퓨터가 알 수 있도록 명확하게 지정해줘야 한다.

선언하면서 값을 저장할 경우에는 '타입 추론'을 통해 컴퓨터가 알아서 타입을 지정한다.

~~~swift
var a: Int // 타입 주석(Type Annotation)
var b = 10 // 타입 추론(Type Inference)
~~~

## 타입 안정성(Type Safety) 
다른 타입끼리 계산이 불가능하다. 다른 타입간에 계산이 필요한 경우, '타입 변환'을 이용해야 한다.
~~~swift
let a = 123.456
let b = Int(a) // 123

/*실수 → 상수 : 기본적으로 소수점 부분을 버리는 함수가 적용됨
(반올림 하는 함수도 존재는 함)*/

let str = "123"
let number1 = Int(str) // Optional(123)

//문자열 → 상수, 실수 : 타입컨버전이 실패할 가능성이 존재하므로 값이 Optional로 저장됨 
~~~
[문자열 타입 컨버전이 실패하는 이유](https://github.com/ksy1342/iOS-Study/blob/main/Swift%20Basic/Type_Conversion.md)

## 타입 애일리어스(Type Alias)
기존에 선언되어있는 타입에 별명을 붙여 코드 가독성을 높이는 문법이다.
~~~swift
typealias Dog = String 
let name: Dog = "초코" 

//주로 긴 타입을 치환할 때 사용?
typealias Something = (Int) -> String
~~~