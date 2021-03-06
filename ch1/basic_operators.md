# 基本運算子

運算子是檢查、改變、合併值的特殊符號或短語。像是加號`+`就是將兩個數相加 (`let number = 1 + 2`)，或是直接讓`i`加 1 的自加運算子`++i`。


### 指派運算子

前面章節已經有多次使用，`a = b`表示將右邊的`b`指派給左邊的`a`。

```swift
let b = 10
var a = 5
a = b // 將 b 指派給左邊的 a
print(a) // 現在 a 等於 10

```


### 數值運算子

Swift 中所有數值型別都支援基本的四則運算，加 `+`、減 `-`、乘 `*`、除 `/` 。

```swift
var a = 1 + 2 // a 等於 3
var b = 7 - 2 // b 等於 5
var c = 3 * 2 // c 等於 6
var d = 10.0 / 2.5 // d 等於 4.0

```

加法運算子也可以用於字串的合併：

```swift
let firstString = "Hello, "
let secondString = "world."
let finalString = firstString + secondString
print(finalString) // 印出 Hello, world.

```

後面章節會介紹更多字串的操作。

#### 餘數運算

餘數運算( `a % b` )是計算`b`的多少倍剛剛好可以容入`a`，返回多出來的那部分，也就是餘數。

`a = (b * 倍數) + 餘數`

以下的例子為`9 = (4 * 2) + 1`，`9`等於`4`乘上倍數`2`再加上餘數`1`。返回的值就是餘數，也就是`1`。

```swift
var number = 9 % 4
print(number) // 餘數等於 1

```

Swift 比較特別的一點是，浮點數也可以取餘數：

```swift
var number = 8.0 % 2.5 // 8.0 = (2.5 * 3.0) + 0.5
print(number) // 餘數等於 0.5

```

#### 自加和自減運算

如果需要自加或自減`1`時，有個簡潔的運算子`++`及`--`，代表的是對這個變數加`1`或減`1`。

```swift
var i = 1
++i // 因為 i 加 1 所以現在 i 等於 2
--i // i 減 1 現在 i 等於 1

```

`++i`也就是`i = i + 1`的簡寫，而`--i`是`i = i - 1`的簡寫。

`++`及`--`既是前綴也是後綴運算子，`++i`、`i++`、`--i`、`i--`都是有效的寫法。前綴與後綴的差別在於返回值的不同，當`++`前綴時，這個變數會先自加再返回，`++`後綴時，則是先返回再自加，例子如下：

```swift
// ++ 前綴
var a = 3
var b = ++a // a 先自加才返回 所以現在 a 跟 b 都是 4

// ++ 後綴
var c = 5
var d = c++ // c 先返回才自加 所以 c 等於 6, d 等於 c 自加前的數值 5

// -- 也是一樣的規則

```

除非需要`i++`的特性，不然建議使用`++i`及`--i`，先自加或自減後才返回，比較符合使用上的邏輯。

#### 一元負號

數值的正負號可以使用前綴`-`（即一元負號）來切換：

```swift
let number = 3
var anotherNumber = -number // 為 -3
var finalNumber = -anotherNumber // 為 3

```

#### 一元正號

一元正號`+`則是不做任何改變地回傳數值。

```swift
let number = -6
var anotherNumber = +number // 為 -6

```


### 複合指派運算子

Swift 提供一個簡潔的方式，將數值運算與指派運算合併，像是`+=`，很多時候可以簡化程式。

```swift
var a = 3
a += 2 // 這行等同於 a = a + 2 的簡寫
print(a) // 現在 a 等於 5

// 其他運算子也是一樣
a -= 4 // a = a - 4 , 現在 a 等於 1
a *= 10 // a = a * 10 , 現在 a 等於 10
a /= 2 // a = a / 2 , 現在 a 等於 5
a %= 2 // a = a % 2 , 現在 a 等於 1

```


### 比較運算子

將兩個數值作比較，並返回這個比較是否成立的布林值，即返回`true`或是`false`，以下是常用的比較運算。

- 等於（`a == b`）
- 不等於（`a != b`）
- 大於（`a > b`）
- 小於（`a < b`）
- 大於等於（`a >= b`）
- 小於等於（`a <= b`）

```swift
1 == 1 // 返回 true 因為 1 等於 1
2 != 1 // 返回 true 因為 2 不等於 1
2 > 1 // 返回 true 因為 2 大於 1
1 < 2 // 返回 true 因為 1 小於2
1 >= 1 // 返回 true 因為 1 大於等於 1
2 <= 1 // 返回 false 因為 2 不小於等於 1

```

常用於條件語句，像是`if`條件：

```swift
var i = 1
if i == 1 {
    print("Yes, it is 1 .")
} else {
    print("No, it is not 1 .")
}

// 因為 i 等於 1, 返回 true, 所以會印出 Yes, it is 1 .

```

後面章節會正式介紹`if`的使用方法。

### 三元運算子

這是一個簡潔的條件式運算：`問題 ? 答案1 : 答案2`。`問題`需要返回一個是否成立的布林值，表示`true`或`false`，如果為`true`，則是返回`答案1`，反之如果為`false`，則是返回`答案2`。也就是下列寫法的簡寫：

```swift
if 問題 {
    答案1
} else {
    答案2
}

```

以下是個例子：

```swift
var score = 25
if score < 60 {
    score = score + 50
} else {
    score = score + 20
}

print(score) // 現在 score 等於 75

```

使用三元運算子可以簡化成下面這樣：

```swift
var score = 25
score = score + (score < 60 ? 50 : 20)

```


### 空值聚合運算子

前面章節介紹過的可選型別， Swift 提供一個簡潔的使用方法：`a ?? b`。先判斷`a`是否為`nil`，如果`a`有值，不是`nil`，就會解析`a`並返回，但如果`a`為`nil`，則返回預設值`b`。也就是下面這個寫法的簡寫：
```swift
a != nil ? a! : b

```

這裡用到前面提到的三元運算子，如果`a`不等於`nil`，則強制解析`a`並返回，否則就返回`b`。以下為一個例子：

```swift
let defaultColor = "red"
var userDefinedColor: String? // 未賦值 所以預設為 nil
var colorToUse = userDefinedColor ?? defaultColor
print(colorToUse) // 未賦值給 userDefinedColor ,所以會返回 defaultColor, 這邊即印出 red

// 反之如果有賦值
var userAnotherDefinedColor: String? = "green"
var anotherColorToUse = userAnotherDefinedColor ?? defaultColor
print(anotherColorToUse) // 這邊即印出 green

```


### 區間運算子

Swift 提供兩個方便表達一個區間的值的運算子。

#### 閉區間運算子

表示方式為：`a...b`，定義一個包含從`a`到`b`(包括`a`和`b`)的所有值的區間。`b`必須大於等於`a`。

```swift
// 1...5 代表的就是 1,2,3,4,5 這五個數字
for index in 1...5 {
    print("\(index) * 5 = \(index * 5)")
}
// 依序印出
// 1 * 5 = 5
// 2 * 5 = 10
// 3 * 5 = 15
// 4 * 5 = 20
// 5 * 5 = 25

```

後面章節會正式介紹`for-in`的使用方法，這邊先理解為是一個會依照規則依序執行動作的語法。

#### 半開區間運算子

表示方式為：`a..<b`，定義一個從`a`到`b`但不包括`b`的區間。`b`必須大於等於`a`，但當`a`等於`b`時，則不會有值。

```swift
// 1..<5 代表的就是 1,2,3,4 這四個數字 不包括 5
for index in 1..<5 {
    print("\(index) * 5 = \(index * 5)")
}
// 依序印出
// 1 * 5 = 5
// 2 * 5 = 10
// 3 * 5 = 15
// 4 * 5 = 20

```


### 邏輯運算子

Swift 支援三個標準邏輯運算。

- 邏輯非（`!a`）
- 邏輯且（`a && b`）
- 邏輯或（`a || b`）

`a`及`b`都是邏輯布林值，且皆會返回一個邏輯布林值，即`true`或是`false`。

#### 邏輯非

`!a`對一個布林值取相反值，即將`true`變`false`，或是將`false`變`true`。這是一個前綴運算子，且不加空格，例子如下：

```swift
let isOpen = false
if !isOpen {
    print("It is open .")
}

```

#### 邏輯且

`a && b`表示只有當`a`跟`b`都為`true`時，才會返回`true`，否則如果`a`或`b`其中一個為`false`，就會返回`false`。

```swift
let isOpen = true
let isWeekend = false
if isOpen && isWeekend {
    print("Success !")
} else {
    print("Failure !")
}

// 因為其中一個為 false 所以會返回 false 即印出 Failure !

```


#### 邏輯或

`a || b`表示只要`a`跟`b`其中一個值為`true`時，就會返回`true`，除非`a`和`b`皆為`false`，才會返回`false`。

```swift
let isSunday = true
let isWeekend = false
if isSunday || isWeekend {
    print("Success !")
} else {
    print("Failure !")
}

// 因為其中一個為 true 就會返回 true 即印出 Success !

```


### 括號優先

以上介紹很多運算子，當一個運算式太複雜時，可以使用括號來標示清楚，同時也用來表明優先級(如同傳統學習數學計算一樣，括號括起來的部份要優先計算)。

```swift
// 數值運算
var number = 3 + 2 * 5 // 先乘除後加減 所以 number 等於 13
var anotherNumber = (3 + 2) * 5 // 括號括起來的優先 所以 anotherNumber 等於 25

// 邏輯運算
let isOpen = false
let isWeekend = true
let isSunday = true

// 由左至右依序判斷
if isOpen && isWeekend || isSunday {
    print("Success !")
} else {
    print("Failure !")
}
// 先作"邏輯且"判斷 isOpen && isWeekend 會返回 false
// 再與後面的 isSunday 作"邏輯或"的判斷 會返回 true
// 所以這邊會印出 Success !

// 括號有優先權
if isOpen && (isWeekend || isSunday) {
    print("Success !")
} else {
    print("Failure !")
}
// 括號優先 所以先做"邏輯或"判斷 isWeekend || isSunday 會返回 true
// 再與前面的 isOpen 作"邏輯且"的判斷 會返回 false
// 所以這邊會印出 Failure !

```

