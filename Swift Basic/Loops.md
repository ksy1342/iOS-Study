## for문
~~~Swift
for i in 1...5 {
    print("hi \(i)")
}
~~~
    hi 1
    hi 2
    hi 3
    hi 4
    hi 5

+ 와일드 카드 패턴
~~~swift
for _ in 1...3 {
    print("hello")
}
~~~
*_는 스위프트에서 생략의 의미*
+ 배열 등의 컬렉션 타입에서 사용 가능
~~~swift
let list = ["a", "b", "c"]

for i in list {
    print(i)
}
~~~
    a
    b
    c
    
+ 문자열도 가능
~~~swift
for str in "Hi" {
    print(str)
}
~~~
    H
    i

+ 특정 함수 활용 가능
~~~swift
for i in (1...5).reversed() {    // 5...1(x)
    print(i)
}
// 5, 4, 3, 2, 1

let range = stride(from: 1, to: 11, by: 2)
let range1 = stride(from: 1, through: 11, by: 2)

for i in range{
    print(i)
}
// to : 1, 3, 5, 7, 9
// through : 1, 3, 5, 7, 9, 11 
~~~

## while문
+ 조건을 만족하는 동안 계속 실행 
+ 무한 반복이 일어날 수 있으므로, while문 내부에서 조건을 변화시켜주는 작업이 필요함
~~~swift
var sum = 0
var num = 1

while num <= 50 {
    sum += num
    num += 1
}

print("1부터 50까지의 합: \(sum)")
~~~
    1부터 50까지의 합: 1275

### * repeat - while문
+ 다른 언어의 do - while문과 동일하다.
+ 조건이 마지막에 있다는 게 차이점이다. -> 코드를 일단 한번 실행한 후, 조건 확인
~~~swift

var number = 5
var sumOfNum = 0


while number < 5 {
    sumOfNum += number
    number += 1
}
~~~
    number == 5
    sumOfNum == 0
~~~swift
number = 5
sumOfNum = 0

repeat {
    sumOfNum += number
    number += 1
} while number < 5
~~~
    number == 6
    sumOfNum == 5

## 제어전송문(Control Transfer Statement)
### 1. continue
+ 해당 루프를 더 이상 진행시키지 않고 다음으로 넘김
~~~swift
for i in 1...10 {
    if i % 2 == 0 {
        continue
    }
    print(i)
}
~~~
    1
    3
    5
    7
    9

### 2. break
+ 반복문 종료
~~~swift
for i in 1...10{
    if i == 4 {
        break
    }
    print(i)
}
~~~
    1
    2
    3

### 3. 중첩 반복문에서 제어 전송문을 원하는 반복문에 사용하는 방법
+ 원칙에 의해 가장 가까운 반복문에 적용
+ Labeled Statements 활용
~~~swift
A: for a in 1...3 {
    B: for b in 1...3 {
        if i == 2 {
            continue A
        }
    }
}
~~~