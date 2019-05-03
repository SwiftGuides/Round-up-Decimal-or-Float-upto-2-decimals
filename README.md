# Round-up-Decimal-or-Float-upto-2-decimals
This Guide ill show you how you can round up or show the long Float or Double values up to 2 decimals 

## Method - 1

Source :- https://stackoverflow.com/a/54372912/10422074

* Using Extension

```swift

extension Double {
    func rounded(digits: Int) -> Double {
        let multiplier = pow(10.0, Double(digits))
        return (self * multiplier).rounded() / multiplier
    }
}

```
* Call it Like this 

```swift

let foo = 3.14159.rounded(digits: 3) // 3.142

```

## Method - 2 
Source :- https://stackoverflow.com/a/49014278/10422074

Use a format string to round up to two decimal places and convert the double to a String.

```swift
let myDouble = 3.141
let doubleStr = Double(String(format: "%.2f", myDouble)) // 3.14

let myDouble = 3.141
let doubleStr = String(format: "%.2f", myDouble) // "3.14"

```

If you want to round up your last decimal place, you could do something like this :

```swift
let myDouble = 3.141
let doubleStr = Double(String(format: "%.2f", ceil(myDouble*100)/100)) // 3.15

let myDouble = 3.141
let doubleStr = String(format: "%.2f", ceil(myDouble*100)/100) // "3.15"

```
