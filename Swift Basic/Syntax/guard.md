## 가드문(guard)
+ if문은 중첩해서 사용할 때, 들여쓰기가 계속 들어가기 때문에 가독성 이슈가 발생함
+ 이러한 단점 극복 -> 들여쓰기 없이 쭉 내려가기 때문에 가독성이 뛰어남

~~~swift
func check(words: String) -> Bool {
    
    guard words.count >= 5 else {
        
        print("5글자 미만입니다.")
        
        return false      
    }
    
    print("\(words.count)글자입니다.")
    
    return true
}

check(words: "안녕하세요")
~~~ 
    5글자입니다.


### 특징

+ if문과 달리 모두 동일한 스코프로 취급되어 변수 사용에 제약이 없음 (guard let 바인딩)
+ 구조상 조기 종료의 조건이 필요하므로, 함수나 반복문 내에서만 사용한다. (return,throw / break,continue)
+ 여러개의 옵셔널타입을 안전하게 처리가능
