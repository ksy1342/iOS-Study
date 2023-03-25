# 딕셔너리(Dictionary)
    각 요소를 'key : value'로 관리하는 컬렉션
## 타입 표기
~~~swift
// 정식 문법
let dic1: Dictionary<String, String> = ["A" : "Age", "B" : "Birth"] 

// 단축 문법
let dic2: [String, String] = []

~~~

## 기본 특징
+ 키 값으로 구분하기 때문에, 키 값은 중복이 불가능하다.
+ 키 값의 타입은 항상 Hashable해야 한다.
+ 이로 인해, 배열보다 검색속도가 빠르다. 
+ 동일한 타입 쌍의 데이터만 담을 수 있다.
+ 밸류값에 딕셔너리나 배열을 사용하여 중첩이 가능하다.

## 기능
### 1. 빈 딕셔너리 생성
~~~swift
let dic1: [String, Int] = [:]
var dic2 = Dictionary<Int, String>()
var dic3 = [Double, Int]()
~~~
*배열과 마찬가지로, 빈 배열만으로는 타입을 유추할 수 없어 에러가 발생한다.*
### 2. 기본 기능
~~~swift
dic1.count 
dic1.isEmpty 
dic1.randomElement() // 네임드 튜플 형태로 리턴
~~~
    2
    false
    (key "B", value "Birth")

~~~swift
dic1.keys  
dic1.values 

dic1.keys.sorted()
dic1.values.sorted()
~~~
    Dictionary.Keys(["A", "B"])
    Dictionary.Values(["Age", "Birth"])

    ["A", "B"]
    ["Age", "Birth"]

### 3. 요소에 접근
+ key값으로 접근
+ value만 검색할 수 있는 방법은 제공하지 않는다.
+ nil이 리턴될 수 있으므로 옵셔널타입으로 리턴된다.
~~~swift
print(dic["A"])
print(dic["F"])
~~~
    Optional("Age")
    nil
*따라서, 값을 사용하고자 할때는 강제 추출이나 바인딩 같은 방법을 사용해야 한다.*

### 4. 업데이트
+ 동일한 키가 있으면 밸류 덮어쓰기
+ 동일한 키가 없으면 추가
~~~swift
// 정식 함수 문법
// wöter.updateValue("Buch", forKey: "B")

var wörter = [String: String]()

wörter["A"] = "Apfel" 
wörter["B"] = "Buch"
wörter["B"] = "Besieger"

wörter
~~~
    ["A" : "Apfel", "B", "Besieger"]
+ 전체 교체 
~~~swift
wörter = ["a" : "apfel"]

wörter
~~~
    ["a" : "apfel"]

### 5. 삭제
~~~ swift
wörter["B"] = nil

wörter.removeValue(forKey: "A")   // 삭제후, 삭제된 값 리턴

// 전체 삭제하기
dic.removeAll()
dic.removeAll(keepingCapacity: true)
~~~
## 비교
+ 키, 밸류 모두 일치하는지 확인
+ 순서 상관없이 비교 가능

## 활용
### 1. 중첩
+ value에 배열 가능
~~~swift
var dic1 = [String: [String]]() 
~~~
+ 딕셔너리도 가능
~~~swift
var dic2 = [String: [Int: Int]]() 
~~~
### 2. 반복문
+ 배열처럼 열거하지 않아도 네임드 튜플로 전달한다.
+ 순서가 존재하지 않으므로, 실행마다 결과가 달라진다.
~~~swift
for dic in dic1 {
    print("\(dic.0) : \(dic.1)")
}

for (key, value) in dic1 {
    print("\(key) : \(value)")
}

for (key, _) in dict {
    print("Key :", key)
}

for (_, value) in dict {
    print("Value :", value)
}
~~~