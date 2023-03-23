## 어트리뷰트 키워드?
+ 컴파일러에게 추가적인 정보를 제공한다.
+ 총 2가지 역할로 분류된다.
  1. 선언에 대한 추가정보
  2. 타입에 대한 추가정보

## @discardableResult
+ @discardableResult도 그중 하나이다.
+ 리턴값이 있는 함수에서 리턴값을 사용하지 않으면, 경고창이 표시된다. 
+ 이것을 제거하기 위해 사용한다.
~~~swift
@discardableResult
func name() -> String {
    print("홍길동")
    return "홍길동"
}

name()
~~~
+ @discardableResult가 추가되지 않은 이전 버전의 스위프트에서는 와일드카드 패턴을 사용했었다.
~~~swift
_ = name()
~~~
