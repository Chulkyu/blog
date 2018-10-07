---
layout: post
title: Swift get & set , didSet & willSet
date: 2018-10-07 22:47:00 +0300
description: About Swift Property get & set , didSet & willSet # Add post description (optional)
img: swift-get-set.png # Add image post (optional)
tags: [Swift, Property, Developer, Apple, Xcode, get, set, didSet, willSet, observer] # add tag
---
#####

------

## *Property get, set, didSet, willSet

#### - property에는 {get, set} 또는 {didSet, willSet} 을 사용 가능

#### - 하나의 property에 {get, set}, {didSet, willSet} 모두 같이 쓸 순 없다

- #### get, set sytax

```swift
class GetSet {

    var storage: Int		// get,set을 사용하기 위해선
   							// 또 다른 storage property가 필요
    init(storage: Int) {
        self.storage = storage
    }


    var intProperty: Int {		// get, set property
        get {					// get만 사용할 땐 get 생략 가능
            return storage - 1	// set만 사용은 불가
        }
        set {
            storage = newValue + 1
        }
    }

    func subscription() {
        print("get is \(intProperty)")
    }	// 읽기 전용인 get property를 사용해 데이터를 읽어온다						
}

let getSet = GetSet(storage: 15)
getSet.subscription()
// "get is 14"
// get은 GetSet 클래스를 인스턴스화 시킬 때 설정해준 초기화 값만 읽어온다.

getSet.intProperty = 16
getSet.storage
// 17
```

------

- ### get, set을 사용하는 경우

#### 1. property에 값이 할당 될 때 적절한 값인지 검증할 때

#### 2. 다른 property 값에 의존적인 property를 관리 할 때

#### 3. property를 private하게 사용하기 위해 [참조](https://medium.com/ios-development-with-swift/%ED%94%84%EB%A1%9C%ED%8D%BC%ED%8B%B0-get-set-didset-willset-in-ios-a8f2d4da5514)

------

#### 1. property에 값이 할당 될 때 적절한 값인지 검증할 때

##### - set의 newValue를 사용하여 property의 값이 바뀌기 전에 확인 가능

```swift
class Company {
    var memberStorage: Int = 0
    var member: Int {
        get {
            return memberStorage
        }
        set {
            if newValue > 0 {
                memberStorage = newValue
            } else {
                print("직원 수는 0명 보다 많아야 합니다.")
            }
        }
    }
}
let company = Company()
company.member = -5		// "직원 수는 0명 보다 많아야 합니다."
company.memberStorage	// 0

company.member = 15
company.memberStorage	// 15

```

------

#### 2. 다른 property 값에 의존적인 property를 관리 할 때

##### - 회사 멤버 저녁식사 비용은 회사 멤버수에 비례(의존적)

##### - get을 활용하여 member 수에 맞춰 memberDinnerCost 계산 가능

##### - get만 사용하였기 때문에 클래스 외부에서 memberDinnerCost는 변경 불가, 오직 member 수에 따라 계산된 값이 반환된다.

```swift
class Company {
    var memberStorage: Int = 0
    var member: Int {
        get {
            return memberStorage
        }
        set {
            if newValue > 0 {
                memberStorage = newValue
            } else {
                print("직원 수는 0명 보다 커야 합니다.")
            }
        }
    }

    var memberDinnerCost: Int {
        get {
            return memberStorage * 10000
        }
    }

}
let dinnerCost = Company()
dinnerCost.member = 15
dinnerCost.memberDinnerCost		// 150000
```

------

- ### didSet, willSet

#### - property observer : 내부적으로 **"초기화 된"** property 값을 감시

- #### didSet : property 값이 변경된 직후에 호출

- #### willSet : property 값이 변경되기 직전에 호출

#### - didSet, willSet을 활용하여 원하는 타이밍에 작업 수행 가능

#### * property observer를 사용하기 위해서는 property의 값이 ''**반드시 초기화**'' 되어 있어야 한다.

#### - 클래스의 init() {} 안에서 값을 할당 할 때는 didSet, willSet은 호출 되지 않음. 초기화 이후부터 property를 감시

```swift
var propertyObserver: Int = 10 {
    didSet(oldValue) {
        // propertyObserver의 값이 변경된 직후에 호출, oldValue는 propertyObserver의 변경 전 값
    }
    willSet(newValue) {
        // propertyObserver의 값이 변경되기 직전에 호출, newValue는 변경 될 새로운 값
    }
}
```

------

- #### didSet, willSet(property observer) 사용하는 경우

#### - 가장 빈번한 사용은 Model에서 갱신된 값을 View에 보여줄 때

#### [MVC](https://medium.com/ios-development-with-swift/mvc-%ED%8C%A8%ED%84%B4-in-ios-7751911f8ca8)

##### - ex) View에 점수를 표시하는 Label이 있다고 가정. 점수가 바뀔 때마다 View의 Label을 업데이트 해주고 싶을 때.

```swift
score = 85
scoreLabel.text = "Score: \(score)"
```

##### - 이렇게 해도 View의 Label은 정상적으로 바뀌지만, 만약 여러곳에서 score의 값을 바꾼다면 score의 값이 바뀌는 곳 마다 scoreLabel.text = "Score: \(score)" 를 적어주어야 한다. (Bad Case)

------

#### - 이럴 때 property observer를 사용할 수 있다.

##### - property observer를 사용하면 score값이 바뀔 때마다 View의 값을 갱신하는 작업을 따로 해줄 필요가 없다.

```swift
var score: Int = 0 {
    didSet {
        scoreLabel.text = "Score: \(score)"
// score의 값이 바뀐 직후 didSet이 실행되어 scoreLabel.text의 값을 바꾼다
    }
}
```

------

#### - 바뀐 값과 바뀌기 전의 값을 비교하는 작업도 가능

```swift
var score: Int = 0 {
   didSet {
      print("현재 점수는: \(score), 이전 점수는: \(oldValue)")
   }
}
score = 5
// "현재 점수는: 5, 이전 점수는: 0"
```

------
