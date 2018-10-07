---
layout: post
title: About Swift Language
date: 2018-10-06 15:35:00 +0300
description: Learning Swift Language
img: swift-Language.jpeg # Add image post (optional)
tags: [Swift, Software, Programming, Xcode, Developer, Apple] # add tag
---


<!-- $theme: Gaia -->

------

# Swift Language

#### - 스위프트는 안전하고 빠르며 상호작용 하는 프로그래밍 언어이다. 폰, 데스크탑, 서버 외 어떤 것에서도 코드를 짜기에 aws ome한 방법이다. 개발하는데 있어 컴파일러와 랭귀지 모두 최적화 되어 있다.

#### - 새로운 프로그래머들도 배우기에 직관적이고 재밌게 배울 수 있다. 플레이그라운드에서 코드를 작성해 보면 빌드를 하거나 앱을 직접 돌려볼 필요 없이 결과를 즉시 알 수 있다.

- #### 변수는 항상 사용전에 initialized를 해주어야 한다.

- #### Array 인덱스 범위를 벗어나는 것을 체크

- #### Optional에서는 nil 값을 핸들링 해주어야 한다.

- #### 메모리 관리를 자동적으로 해준다

- #### 예기치 않은 오류의 처리 방법을 제안

#### - Swift는 타입 추론, 패턴 매칭, 간결한 syntax를 결합하여 복잡한 Ideas를 명확하고 간결하게 표현할 수 있다. 덕분에 코드는 쓰기 쉬울 뿐만 아니라 읽고 유지보수 하기도 쉽다.

------

# * A Swift Tour

#### swift에서 "Hello, World"를 print하기는 매우 간단하다.

```swift
print("Hello, world")
```



- ### Simple Values

#### use **'let'**  to make a constant, **'var'** to make a variable

#### - 변수는 항상 사용전에 initialized를 해주어야 한다.

```swift
var myVariable = 42
myVariable = 50
let myConstant = 42
```



#### - 변수에 값을 바로 넣어주지 않을 때에는 타입을 명확히 정해주어야 한다.

```swift
var myVariable: Int
myVariable = 42
myVariable = 50
let myConstant: Int
myConstant = 42
```



#### - Swift에서는 변수의 값이 명확하다면 자동으로 **'타입추론'**이 되기 때문에 타입을 굳이 적어줄 필요가 없다.(타입을 정해주어야 할 경우에만 타입 지정)

```swift
let explicitDouble: Double = 70	// type Double
let expliciFloat: Float = 70	// type Float

let implicitInteger = 70	// type Int
let implicitDouble = 70.0	// type Double
```

------

#### - 타입이 정해지면 변수에 다른 타입의 값을 넣을 수 없으며, 타입이 다른 변수와는 연산이 불가능하다.

```swift
let label = "The width is"	// type String
let width = 94				// type Int
label = 15					// error String != Int
width = "The Label is"		// error Int != String
let widthLabel = label + width // error String + Int
```



#### - 이를 가능하게 하기 위해서는 type convert(타입 전환)을 해주어야 한다.

#### 1. 변환시킬 타입을 앞에 적어주기

```swift
let widthLabel = label + String(width)
// "The width is 94
// (label: String) + (width: Int -> String)
```

#### 2. 보간법 : 백슬러시 (width)

##### - 숫자열을 문자열로 타입변환 시킬 때 사용

```swift
let apples = 3	// type Int
let oranges = 5	// type Int
let appleSummary = "I have \(apples) apples."
// "I have 3 apples."
let fruitSummary = "I have \(apples + oranges) pieces of fruit."
// "I have 8 pieces of fruit."

let strawberries = 2	// type Int
let bananas = 4.5		// type Double
let fruitSummary2 = "I have \(strawberries + bananas) pieces of fruit."
// error \(strawberries + bananas)
// error can't \(Int + Double)

let height = 180.3
let weight = 73.6
let introduce = "Hi, my height is \(height), weight is \(weight). Am I healthy? "
// "Hi, my height is 180.3, weight is 73.6. Am I healthy?"
```

------

#### - quotation(인용구) marks(""") : 변수에 여러줄의 문장을 입력할 때 사용

```swift
let quotation = """ Even though there's whitespace to the left, the actual lines aren't indented. Except for this line. Double quotes can appear without being escaped. """
```

------

#### - Using brackets([ ]) : array, dictionary 만들 때 사용

##### * array는 인덱스 값이 있어서 데이터가 차례대로 저장되지만, dictionary는 데이터가 저장되는 순서가 따로 없고 랜덤으로 지정된다. 그렇기에 key 값을 사용하여 호출한다.

#### 접근 방법 array[index], dictionary["key"]

```swift
// array
var shoppingList = ["catfish", "water", "tulips"]
shoppingList[1] = "bottle of water"
/* print(shoppingList)
 ["catfish", bottle of water", "tulips"]
*/

// array 요새 추가하기
shoppingList.append("blue paint")
/* print(shoppingList)
 ["catfish", "bottle of water", "tulips", "blue paint"]
*/

// dictionary
var occupations = ["Malcolm": "Captain","Kaylee": "Mechanic",]
occupations["Jayne"] = "Public Relations"
/* print(occupations)
 ["Malcolm": "Captain","Kaylee": "Mechanic", "Jayne": "Public Relations"]
*/
```

------

#### - 빈(empty) array, dictionary 만들기, use the initializer syntax

```swift
let emptyArray = [String]()
let emptyDictionary = [String: Float]()
//array 와 dictionary 도 마찬가지로 값을 나중에 입력할 때는 타입을 명확히 적어주어야 한다.
```

------

#### - 타입을 유추(이미 한번 타입이 정해졌던 경우) 할 수 있을 경우 빈 array, dictionary

##### - for example, when you set a new value for a variable or pass an argument to a function

```swift
shoppingList = ["catfish", "bottle of water", "tulips", "blue paint"]
shoppingList = []

occupations = ["Malcolm": "Captain","Kaylee": "Mechanic", "Jayne": "Public Relations"]
occupations = [:]
```

------

- ### Control Flow

#### - if, switch 조건문

#### - for-in, while, repeat-while 반복문

```swift
// 조건문
if <condition> {
    <code>
}
/* if문의 <condition>은 'true or false'로 나올 수 있는
	Bool 타입의 조건이어야 한다. */

switch <value> {
case <pattern>:
    <code>
default:
    <code>
}

// 반복문
for <item> in <items> {
    <code>
}

while <condition> {
    <code>
}

repeat  {
    <code>
} while <condition>

```

------

```swift
let individualScores = [75, 43, 103, 87, 12]
var teamScore = 0
for score in individealScores {
    if score > 50 {
        teamScore += 3
    } else {
        teamScore += 1
    }
}
print(teamScoer)
// "11"

/* individualScores 어레이의 요소들을 하나씩 꺼내어
	score에 대입하여 조건문의 결과에 따라
	teamScore 변수에 +3 또는 +1 을 해주는 반복문
	teamScore +=3 은
	teamScore = teamScore +3 와 같은 표현

반복문 실행
	teamScore = 0
if	75 > 50   true		 --> +3 	  teamScore = 3
if	43 > 50   false  else --> +1      teamScore = 4
if	103 > 50  true	      --> +3	  teamScore = 7
if	87 > 50   true  	  --> +3	  teamScore = 10
if	12 > 50   false	 else --> +1      teamScore = 11
```

------

##### - for-in 반복문은 반복범위를 지정해 줄 수 있다.

```swift
var total = 0
for i in 0..<4 {
    total += i
}
print(total)
// Prints "6"
// 0~3까지 반복
```



#### - dictionary 타입을 for-in 반복문에 넣게 되면 어떤 값이 먼저 반복문에 들어가서 실행될지 알 수 없다.

##### *(dictionary는 unordered collection이기 때문에 랜덤으로 추출된다)

```swift
let interestingNumbers = [
    "Prime": [2, 3, 5, 7, 11, 13],
    "Fibonacci": [1, 1, 2, 3, 5, 8],
    "Square": [1, 4, 9, 16, 25],
]
var largest = 0
for (kind, numbers) in interestingNumbers {
    for number in numbers {
        if number > largest {
            largest = number
        }
    }
}


/* print(largest)
   25

interestingNumbers는 value 값이 array타입을 가지는 dictionary 타입이다.
(type of interestingNumbers) --> dictionary

for (kind, numbers) in interestingNumbers 에서

kind 에 key 값인 "Prime" , "Fibonacci" , "Square" 중 랜덤으로 하나씩 들어오게 되고
numbers에 해당 key 값의 value인 array가 들어오게 된다.

그런 다음, 아래의 반복문에서는 해당 key 값의 value 값인 array가 다시 한번 차례대로 추출되어 if 조건문을 실행하게 된다.
for number in numbers {
        if number > largest {
            largest = number
        }
    }

결국 모든 key값의 value(array)의 숫자들이 하나씩 추출되어 조건문을 실행해서 가장 큰 수가 largest의 변수에 최종적으로 들어가게 된다.
```

------

#### - while, repeat-while

##### - while문은 조건을 만족하면 코드가 실행

##### - repeat-while문은 최소한 한번은 코드를 실행하고 조건 비교

```swift
var n = 2
while n < 100 {
    n *= 2
}
print(n)
// Prints "128"

var m = 2
repeat {
    m *= 2
} while m < 100
print(m)
// Prints "128"

/* 위의 상황에선 while문과 repeat-while문의 차이가 없는 것 처럼 보이지만 조건을 1보다 작을 때로 변경하여 주면 값이 달라진다. */


var n = 2
while n < 1 {
    n *= 2
}
print(n)
// Prints "2"
// n < 1  조건문을 만족하지 않기 때문에 코드가 한번도 실행되지 않았다.

var m = 2
repeat {
    m *= 2
} while m < 1
print(m)
// Prints "4"
// m *=2 가 먼저 실행되어 m = 4 가 된 뒤 조건문 m < 1 을 진행하였기 때문에 m = 4 가 된다.
```









#### - if let (Optional Binding)

#### if 를 let 과 같이 쓰게 되면 옵셔널을 바인딩 할 수 있다.

##### * 옵셔널 바인딩 : 옵셔널 타입인 변수 안에 값이 들어 있으면 그 값을 그대로 가져오고 값이 없을 경우 nil을 반환한다.

#### [Video About Optional](https://www.youtube.com/watch?v=a2yd_koVPZ8&list=PLE0Is7fZwoLCVNgtnzf3KR6FRPkSo-_09&index=6)

#### [Site About Optional](https://chulkyu.github.io/blog/Optional/)

```swift
var optionalString: String? = "Hello"
print(optionalString == nil)
// fasle
//optionalString 변수에는 "Hello"라는 스트링 값이 들어가 있기 때문에 nil이 아니다.

var optionalName: String? = "John Appleseed"
var greeting = "Hello!!!!!"
if let name = optionalName {
    greeting = "Hello, \(name)"
}
/* print(greeting)
 "Hello, John Appleseed"

	optionalName 에 "John Appleseed" 값이 들어있기 때문에
	name = "John Appleseed" 들어가게 되고
	조건을 만족(true)하였기 때문에 조건문 안의
	greeting = "Hello, \(name)" 이 실행된다. */


optionalName = nil
if let name = optionalName {
    greeting = "Hello, \(name)"
}
/* print(greeting)
	"Hello!!!!!"

optionalName 이 nil 이기 때문에 조건문의 조건을 만족하지 못하고(false) 조건문 안의 코드가 아예 실행되지 않기 때문에
greeting의 값은 변함지 않는다. */

```

------

#### - 물음표 두개 ?? 를 써서 옵셔널 값을 다룰 수도 있다.

```swift
let nickName: String? = nil
let fullName: String = "John Appleseed"
let informalGreeting = "Hi \(nickName ?? fullName)"

/* nickName ?? fullName
	nickName 에 nil이 아닌 값이 들어 있다면 그 값을 반환하고
	값이 없고 nil 이면 fullName의 값을 대신 반환시키는 코드

print(infromalGreeting)
"Hi John Appleseed"

nickName이 nil이기 때문에 fullName의 값을 가져오게 된다.
*/
```

------

#### - Switch  모든 종류의 데이터와 다양한 비교 작업을 지원

##### -  조건이 반드시 Bool 타입일 필요 없다.

##### * 반드시 default 를 지정해 주어야 한다.

##### (모든 경우에 대한 case를 모두 지정해 주었을 시에만 default 생략 가능 :  모든 경우에 대한 case를 다 지정해 주었기 때문에 default로 빠질 일이 없기 때문)

##### - 첫번째 case부터 차례대로 조건이 맞는지 체크하고 조건이 맞지 않으면 다음 case로 넘어간다. 조건이 맞는 case를 찾으면 해당 case의 코드를 실행하고 switch문을 빠져나온다.

##### 그렇기 때문에 각 case마다 break를 적어줄 필요가 없다.

##### switch문에서 맞는 case가 없을 경우 마지막 default로 빠져서 default의 코드를 실행하게 된다.

```swift
let vegetable = "red pepper"
switch vegetable {
case "celery":
    print("Add some raisins and make ants on a log.")
case "cucumber", "watercress":
    print("That would make a good tea sandwich.")
case let x where x.hasSuffix("pepper"):
    print("Is it a spicy \(x)?")
default:
    print("Everything tastes good in soup.")
}
// Prints "Is it a spicy red pepper?"
```

------

- ### Functions and Closures

```swift
func <name>(<argument> <parameter>: <type>) -> <return type> {
    <code>
}
<name>(<argument>: <value>)


func greet(person: String, day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet(person: "Bob", day: "Tuesday")

/* argument : 함수 외부에서 호출할 떄 쓰는 이름
   parameter : 함수 내부에서 호출할 때 쓰는 이름

greet fuction처럼 argument, parameter를 구분하지 않고 하나로 쓰게 디면 함수 내부에서나 외부에서 모두 같은 이름으로 호출하여 쓴다.
*/

func greet(_ person: String, on day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet("John", on: "Wednesday")

/* argument에 _ 를 쓰게 되면 함수 외부에서 호출할 때 argument를 생략하여 쓸 수 있다.
```

------

#### - 반환 타입을 tuple로 지정하면 여러개의 반환값을 가질 수 있다.

##### - tuple은 array와 비슷하지만 하나의 타입이 아닌 모든 타입의 요소를 담을 수 있다.

```swift
func calculateStatistics(scores: [Int]) -> (min: Int, max: Int, sum: Int) {
    var min = scores[0]
    var max = scores[0]
    var sum = 0

    for score in scores {
        if score > max {
            max = score
        } else if score < min {
            min = score
        }
        sum += score
    }

    return (min, max, sum)
}
let statistics = calculateStatistics(scores: [5, 3, 100, 3, 9])
print(statistics.sum)
// Prints "120"
print(statistics.2)
// Prints "120"
/* statistics.0 -> min = 3
   statistics.1 -> max = 100
   statistics.2 -> sum = 120
*/
```

------

#### - Fuctiond은 다른 함수 내부에서도 선언하고 사용할 수 있다.

##### 하지만 코드가 길어지고 복잡해 지는 단점이 있다.

```swift
func returnFifteen() -> Int {
    var y = 10
    func add() {
        y += 5
    }
    add()
    return y
}
returnFifteen()

// 15

/* returnFifteen() 함수 안에 func add() { y += 5 } 함수를 선언하고 add() 로 함수 실행
```

------

#### - Function은 [first-class type](https://ko.wikipedia.org/wiki/%EC%9D%BC%EA%B8%89_%EA%B0%9D%EC%B2%B4)

- ##### 다른 function의  return 값으로도 사용 가능

```swift
func makeIncrementer() -> ((Int) -> Int) {
    func addOne(number: Int) -> Int {
        return 1 + number
    }
    return addOne
}
var increment = makeIncrementer()
increment(7)
// 8

/* makeIncrementer 함수는 Int를 반환 받아서 다시 Int로 반환 시키는 함수이다.

   increment 는 makeIncrementer 함수를 실행시키는 변수
   increment(7) 을 실행 시키면
   addOne 함수에서 7을 input 값으로 받아 실행하고
   return 1 + 7 을 반환하게 된다.
   makeIncrementer 함수는 addOne를 반환 한다고 되어 있는데
   addone 함수의 반환값이 8 이므로 이를 반환하게 된다.

*/

```

- ##### 다른 function의 argument로도 사용 가능

```swift
func hasAnyMatches(list: [Int], condition: (Int) -> Bool) -> Bool {
    for item in list {
        if condition(item) {
            return true
        }
    }
    return false
}
func lessThanTen(number: Int) -> Bool {
    return number < 10
}
var numbers = [20, 19, 7, 12]
hasAnyMatches(list: numbers, condition: lessThanTen)
// true

/*
1. hasAnMatches 함수는 Int를 요소로 가지는 array 타입의 'list'와
   Int를 받아 Bool 타입을 반환하는 타입의 'condition'
   이 두가지의 파라미터를 받아서 Bool 타입을 반환하는 함수이다.

2. lessThanTen 함수는 Int를 number로 입력 받아서
   number < 10 이면 true, 아니면 false를 반환하는 함수

3. numbers 변수는 [20, 19, 7, 12]. Int 요소를 가지고 있는 array


hasAnyMatches(list: numbers, condition: lessThanTen) 실행
numbers의 array에 있는 요소들을 하나씩 꺼내어 lessThanTen 함수를 통해 true, false 를 반환.
numbers의 요소중 하나라도  number < 10 조건을 만족하면 hasAnyMatches 함수는 true를 반환하게 되고, number < 10 조건을 만족하는 요소가 하나도 없으면 false를 반환하게 된다.

numbers의 요소중 7 이 number < 10 조건을 만족하여 true를 반환하므로 7 다음의 12는 확인하지 않고 바로 true를 반환하게 된다.

```

------



- ### Closure

#### - fucntion을 다른 함수 내부에서 선언하여 실행하거나

#### 다른 함수의 argument로 호출하여 쓰거나

#### 다른 함수의 return 값으로도 호출하여 쓸수 있는 것을 보았다.



#### - Closure는 함수를 func를 사용하여 따로 선언하지 않고도

#### {    } 안에 이름 없는 함수를 만들어 사용하는 것

```swift
{  (<argument parameter: type>) in <code> return <item> }
```

```swift
var numbers = [20, 19, 7, 12]

numbers.map({ (number: Int) -> Int in
    let result = 3 * number
    return result
})
// [60, 57, 21, 36]
// numbers.map 이 받을 인자로 closure가 들어갔다.

numbers.map({ (number: Int) -> Int in
             if number % 2 == 1 {
                 return 0
             }
             let result = 3 * number
             	return result
            } )
// 60, 36
/* odd numbers 가 들어오면 0을 반환하고
   even numbers 가 들어오면 result를 반환
*/

```

#### * closure를 더 간결하게 만들 수 있는 몇가지 옵션

#### - closure의 타입을 이미 알고 있다면 parameter 나 return 타입, 또는 둘 다 생략 가능

```swift
var numbers = [20, 19, 7, 12]
let mappedNumbers = numbers.map( { number in 3 * number })
print(mappedNumbers)
// [60, 57, 21, 36]
/* parameter의 타입은 numbers의 타입이 [Int]이어서 이미 알고 있고
   return 타입은 .map에 의해 결정되므로 굳이 적지 않고 생략해 주어도 된다.
```

#### - parameter 의 이름 대신 $0 같은 번호로 대신 쓸 수 있다.

#### 짧은 closure에서 매우 유용

#### - function 의 argument 중 마지막이 closure라면 괄호() 다음에 closure를 써줄 수 있다.

#### - function 의 유일한 argument 가 closure라면 괄호() 자체를 생략 가능

```swift
let sortedNumbers = numbers.sorted { $0 > $1 }
print(sortedNumbers)
// [20, 19, 12, 7]
```

------

- ### Objects and Classes

#### - class declaration

##### - class 선언은 일반 func과 같은 방식이며 상속 받을 클래스나 delegate가 있으면 class 타입에 적어주면 된다.

##### - class 안에서 변수, 함수 선언은 똑같이 해주면 된다.



```swift
class <name>: <super class> {
        <code>
    }

class Shape {
    var numberOfSides = 0
    let name = "triangle"
    func simpleDescription() -> String {
        return "A shape with \(numberOfSides) sides."
    }
    func angle(side: Double) -> String {
        return "Total sum of \(name)'s angles is 180"
    }
}

```

------

#### - class instance화

##### 변수에 classname 뒤 괄호() 를 붙여 넣어주면 된다.

```swift
let <name> = <classname>()

let shape = Shape()
shape.numberOfSides = 7
var shapeDescription = shape.simpleDescription()

```

------

#### - class 내에서도 변수는 초기화 값을 지정해 주어야 한다.

#### [About Initialization](https://chulkyu.github.io/blog/Swift-Initialization/)

```swift
class NamedShape {
    var numberOfSides: Int = 0	// init 기본 설정 값
    var name: String

    init(name: String) {		// init 저장 속성 값
        self.name = name
    }

    func simpleDescription() -> String {
        return "A shape with \(numberOfSides) sides."
    }
}

let namedShape = NamedShape(name: "maru")
```

------

#### - class 상속

##### - 상속 받을 superClass가 있다면 class 선언할 때 클래스 이름 뒤 콜론(:) 다음에 superClass 이름은 적어주면 된다.

##### - superClass를 상속 받으면 superClass가 가지고 있던 property, method 모두 상속 받게 된다.

##### - 상속 받을 시 super.init(){} 을 해서 superClass의 init을 다시 한번 정의해주는 것이 좋다

##### - init은 앞에 override를 붙여줄 필요가 없지만 superClass에서 상속 받은 method 앞에는 override를 붙여주어야 한다.

```swift
class <name>: <super class> {
        <code>
    }

class NamedShape {
    var numberOfSides: Int = 0	// init 기본 설정 값
    var name: String

    init(name: String) {		// init 저장 속성 값
        self.name = name
    }

    func simpleDescription() -> String {
        return "A shape with \(numberOfSides) sides."
    }
}
let shape = NamedShape(name: "Triangle")
shape.simpleDescription()
// "A shape with 0 sides."


// Square 클래스는 위의 NamedShpe 클래스를 상속 받는다.
class Square: NamedShape {
    var sideLength: Double		// Square 클래스만의 property


    init(sideLength: Double, name: String) {
        self.sideLength = sideLength
        super.init(name: name)// super.init을 사용해 부모클래스의
        numberOfSides = 4	  // property를 호출해 재정의 해준다.
    }

// Square 클래스의 method
    func area() -> Double {
        return sideLength * sideLength
    }

// 부모 클래스의 method를 수정해서 사용하려면 override를 붙여주어야 한다.
    override func simpleDescription() -> String {
        return "A square with sides of length \(sideLength)."
    }
}
let test = Square(sideLength: 5.2, name: "my test square")
test.area()
// 27.04

test.simpleDescription()
// "A square with sides of length"
```

------

#### - NamedShape 클래스의 또 다른 subClass 'Circle'

```swift
class Circle: NamedShape {

    var radius = 0.0

    override init(name: String) {// init 설정 값의 parameter가
        super.init(name: name) // 부모 클래스의 parameter와 같으면
        numberOfSides = 0		// override 키워드를 써줘야 한다.
    }

    func circleRadius(diameter: Double) -> Double {

        radius = diameter / 2

        return radius
    }

    override func simpleDescription() -> String {
        return "\(name) radius is \(radius)"
    }
}

let circle = Circle(name: "Circle4")

circle.circleRadius(diameter: 137)
circle.radius
// 68.5

circle.simpleDescription()
// "Circle4 radius is 68.5"

```

------

#### - EquilateralTriangle 클래스의 이니셜라이저 Steps

##### 1. EquilateralTriangle(하위 클래스)의 변수 선언.

##### 2. super.init 으로 상위 클래스(NamedShape) 이니셜라이저 호출

##### 3. 상위 클래스에서 정의된 변수값 변경.

##### 나머지 method 설정 및 새로운 property(get,set) 설정

```swift
class EquilateralTriangle: NamedShape {
    var sideLength: Double = 0.0

    init(sideLength: Double, name: String) {
        self.sideLength = sideLength
        super.init(name: name)
        numberOfSides = 3
    }

    var perimeter: Double {
        get {
            return 3.0 * sideLength
        }
        set {
            sideLength = newValue / 3.0
        }
    }

    override func simpleDescription() -> String {
        return "An equilateral triangle with sides of length \(sideLength)."
    }
}
var triangle = EquilateralTriangle(sideLength: 3.1, name: "a triangle")
print(triangle.perimeter)
// Prints "9.3"   (get)

triangle.perimeter = 9.9
print(triangle.sideLength)
// Prints "3.3"   (set)

```

------
