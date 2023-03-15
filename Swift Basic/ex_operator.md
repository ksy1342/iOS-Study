## 삼항 연산자
+ if문과 유사하지만 한정적인 쓰임새
+ 주로 2가지 값 중 조건에 따라 한가지를 대입할 때 사용
+ 앱 제작에서 자주 사용
~~~swift
var result = score >= 70 ? 통과 : 탈락
~~~

## 범위 연산자
+ swith문 case
+ for문
~~~swift
for i in 0..<count {
    print("Person \(i + 1) is called \(names[i])")
}
~~~

+ 배열의 서브스크립트 문법
~~~ swift

names[...2]

names[..<1]

~~~
