### swift 공식문서에 의하면,fallthrough를 사용할때 그 다음 case 블럭에 바인딩이 와서는 안됨.

+ 오류가 발생한 코드
~~~swift
let iOS = (language: "swift", version: 5.3)

switch iOS {
 case ("swift",_) :
   print("언어: swift")
   fallthrough
 case let (_,y) where y == 5.3:
   print("최신 버전입니다.")
 default:
   break
}
~~~
+ 올바르게 수정한 코드
~~~swift
switch iOS {
 case let (_,y) where y == 5.3:
   print("최신 버전입니다.")
   fallthrough
 case ("swift",_) :
   print("언어: swift")
 default:
   break
}
~~~