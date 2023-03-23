# 배열(Array)
    데이터를 순서대로 저장하는 컬렉션

## 타입 표기
+ 정식문법
~~~swift
var numArray1: Array<Int>
~~~
+ 단축문법
~~~swift
var numArray2: [Int]
~~~


## 빈 배열 형성
~~~swift
let emptyArray1: [Int] = []

let emptyArray2 = Array<Int>()

let emptyArray3 = [Int]()
~~~

## 기능
### 1. 기본 기능
~~~swift
var numsArray = [1, 2, 3, 4, 5]

numsArray.count // 5

numsArray.isEmpty // false

numsArray.contains(1) // true

numsArray.randomElement() // 랜덤

numsArray.swapAt(0, 1) // [2, 1, 3, 4, 5]
~~~

### 2. 배열의 요소에 접근
~~~swift
numsArray[0]
~~~
~~~swift
numsArray.first   // Optional(1) -> 빈 배열이라면 nil 리턴
numsArray.last
~~~
~~~swift
numsArray.startIndex // 0

numsArray.endIndex  // 5

numsArray[numsArray.endIndex - 1] // numsArray[4]
~~~
~~~swift
var numsArray = [1, 2, 5, 3, 4, 5]

numsArray.firstIndex(of: 5) // 2

numsArray.lastIndex(of: 5) // 5
~~~