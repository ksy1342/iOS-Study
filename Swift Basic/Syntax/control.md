# 제어전송문
## break
### 1. switch
+ 해당 케이스에서 실행하는 문장이 없을경우, 반드시 입력
### 2. 반복문
+ 인접한 반복문을 중지
~~~swift
for index in 1...10 {

    if index == 3 {
        break
    }

    print(index)
}
~~~
    1
    2

## fallthrough
+ switch문에서, 다음 케이스의 문장을 조건비교 없이 무조건 실행  

## continue
+ 반복문에서, 다음 사이클로 넘김

## return
### 1. 리턴타입이 있을 때
+ 리턴값을 나타냄
### 2. 리턴타입이 없을 때
+ 함수의 실행을 중단

## throw
+ 에러가 발생할 수 있는 throwing 함수에서 사용
