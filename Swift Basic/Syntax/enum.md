# 열거형(Enumerations)
    사용자 정의 타입
    연관된 케이스들을 하나의 이름으로 묶은 타입이다.

## 타입 표기
+ 타입의 이름은 대문자로, 케이스는 소문자로 시작해야 한다.
~~~swift
enum Weekend {
    case saturday, sunday
}

enum Animal {
    case dog
    case cat
    case pig
    ...
}
~~~

## 기본 특징
+ 열거형 타입을 가질경우, 그 값은 미리 정의해둔 케이스에서 벗어날 수 없다.
+ 코드의 가독성 / 처리 시 안정성이 높아진다. 
+ 타입이 열거형으로 확정된 변수나 상수라면 타입생략도 가능
~~~ swift
var today = Weekday.monday
var today: Weekday = .sunday

today = .tuesday
// var today = .friday (x)
~~~

+ 특정 케이스만 처리
~~~swift
if today == .sunday {
    
}
~~~
+ 모든 상황별 처리 : 스위치문과 찰떡궁합
~~~swift
switch today {
case .monday:
    print("오늘은 월요일입니다.")
case .tuesday:
    print("오늘은 화요일입니다.")
case .wednesday:
    print("오늘은 수요일입니다.")
case .thursday:
    print("오늘은 목요일입니다.")
case .friday:
    print("오늘은 금요일입니다.")
case .saturday:
    print("오늘은 토요일입니다.")
case .sunday:
    print("오늘은 일요일입니다.")
}
~~~
## 원시값(Raw value)

## 연관값(Associated Values)
