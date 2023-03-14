#### 문자열 -> 숫자 변환 시 타입컨버전이 실패할 가능성이 존재하므로 값은 Optional로 저장된다.
~~~
let str = "123"
let number1 = Int(str) // Optional(123)

let str = "치즈김밥"
let str2 = Int(str) // nil
~~~
