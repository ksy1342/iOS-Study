    *
    **
    ***
    ****
    *****
반복문으로 출력 시도

~~~swift
for i in 1....5 {
    for _ in 1...i {
        print("*")
    }
}
~~~
    *
    *
    *
    *
    *
    ...

### print함수


      print(Any..., separator: " ", terminator: "\n")
   
   
+ 프린트 함수는 이게 원래의 형태이고, 파라미터에 기본 값이 입력된 채 생략되어 있다. 

+ 따라서 같은 줄에서 연속 출력하고 싶을 경우 'terminator' 부분만 따로 입력해 주면 해결.
~~~swift
for i in 1....5 {
        print("*", terminator: "")
}
~~~
    *****
다만 이대로 처음의 반복문에서 사용하게될 경우, 가로로만 출력되었음.
    
    ***************
따라서, 루프마다 줄바꿈이 필요.
~~~swift
for i in 1....5 {
    for _ in 1...i {
        print("*", terminator: "")
    }
    print() // print("\n")과 동일
}
~~~

