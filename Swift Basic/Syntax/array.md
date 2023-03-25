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
### 3. 삽입
~~~swift
var number = [1, 2, 3, 5, 6]

number.insert(4, at: 3)
number.insert(contentsOf: [7,8,9], at: 6)
~~~

### 4. 교체
~~~swift
number[0] = 10
~~~
+ 범위로 교체
~~~swift
number[0...2] = [10, 11, 12]
~~~
+ 범위 삭제
~~~swift
number[0...2] = []
~~~

### 5. 추가
~~~swift
number += [10]
number.append(11)
~~~

### 6. 삭제

~~~swift
alphabet = ["A", "B", "C", "D", "E", "F", "G"]
~~~
+ 요소 개별 삭제
~~~swift
alphabet.remove(at: 2) 

alphabet.removeFirst()   // 맨 앞에 요소 삭제하고 삭제된 요소 리턴 
alphabet.removeFirst(2)   // 앞의 두개의 요소 삭제 ===> 리턴은 안함


alphabet.removeLast()   // 맨 뒤에 요소 삭제하고 삭제된 요소 리턴
alphabet.removeLast(2)  // 리턴 x
~~~
+ 범위 삭제
~~~swift
alphabet[0...2] = [] 
alphabet.removeSubrange(0...2)
~~~

+ 모두 삭제
    + 통째로 제거
    + 저장 공간은 보관 (추후 새 공간을 만들고 저장하는 거보다 미세하게 빠름)
~~~swift
alphabet.removeAll()
alphabet.removeAll(keepingCapacity: true)
~~~
### 7. 기타
+ 정리
    + **동사** : 원본을 직접 수정
    + **동사ing / 동사ed** : 원본을 건드리지는 않고, 정리된 새로운 배열을 리턴
~~~swift
// 오름차순
nums.sort()   
nums.sorted() 

// 내림차순
nums.reverse()   
nums.reversed()

// 랜덤
nums.shuffle()
nums.shuffled()
~~~

## 배열간 비교 가능
+ 같은 타입끼리 비교 가능
+ 개별 요소, 저장 순서를 비교하여 Bool값 리턴

## 활용
### 1. 특정 요소 삭제

### 2. 반복문과 배열
+ .enumerated() : Named 튜플 형태로 한개씩 전달
~~~swift
nums = [10, 11, 12, 13, 14]
~~~
    (offset: 0, element: 10)
    (offset: 1, element: 11)
    .
    .
    .
1 ) 오름차순
~~~swift
for tuple in nums.enumerated() {
    print("\(tuple.0) - \(tuple.1)")
}
~~~
    0 - 10
    1 - 11
    .
    .

2 ) 내림차순
~~~swift
for (index, value) in nums.enumerated().reversed() { 
    print("\(index) - \(value)")
}
~~~
    4 - 14
    .
    .
    .