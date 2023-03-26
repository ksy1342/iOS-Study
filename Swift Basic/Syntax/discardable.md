## @discardableResult

+ 리턴값이 있는 함수에서 리턴값을 사용하지 않으면, 경고창이 표시된다. 
+ 컴파일러에게 굳이 이 리턴값을 이용하지 않아도 된다는 정보를 제공하여, 경고창을 제거하기 위해 사용한다.
~~~swift
@discardableResult
func name() -> String {
    print("홍길동")
    return "홍길동"
}
~~~
