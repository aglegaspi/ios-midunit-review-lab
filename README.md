## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased** √

Input: `Hello, there`

Output: `HELLO, THERE`

```swift
let Message = "Hello, There"

var returnMessage = ""

for letter in Message {
    returnMessage += letter.uppercased()
}

print(returnMessage)

```

2. **Given a String, return a String alternating between uppercase and lowercase letters** √


Input: `Hello, there`

Output: `HeLlO, tHeRe`

```swift
let message2 = "Hello, there"
var returnMessage2 = ""

for (index, letter) in message2.enumerated() {
    if index % 2 == 0 {
        returnMessage2 += letter.uppercased()
    } else {
        returnMessage2 += String(letter)
    }
}
print(returnMessage2)
```

3. **Given a String, return a String with all occurrences of a given letter removed** √

Input: `Hello, there`

Output: `Hllo, thr`

```swift
let message3 = "Hello, there"
var output3 = ""

for letter in message3 {
    if letter != "e" {
        output3 += String(letter)
    }
}

print(output3)
```





## Arrays


1. **Given an array of type [Int], return the largest element** √

Input: `[1,5,2,4,1,4]`

Output: `5`

```swift
let arr = [1,5,2,4,1,4]

if let result = arr.max() {
    print(result)
}
```

2. **Given an array of type [Int], return the smallest element** √

Input: `[1,5,2,4,1,4]`

Output: `1`

```swift
let arr = [1,5,2,4,1,4]

if let result = arr.min() {
    print(result)
}

```

3. **Given an array of type [Int], return its sum** √

Input: `[1,5,2,4,1,4]`

Output: `17`

```swift
let arr = [1,5,2,4,1,4]
let result = arr.reduce(0, +)

print(result)
```

4. **Given an array of type [Double], return its average** √

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`

```swift
let arr4 = [3,4.5,7.5,2,1]
let sum = arr4.reduce(0, +)
let output = Double(sum) / Double(arr4.count)
```

5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number** √

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`

```swift
let arr5 = [3,4.5,7.5,2,1]
let greatethan = 3.0
var result5 = arr5.filter {$0 > greatethan}.reduce(0, +)
print(result5)

```

6. **Given an array of type [Double], return the product of all the elements** √

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`

```swift 
let arr6 = [3,4.5,7.5,2,1]

let output = arr6.reduce(1,*)
print(output)
```

7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`

```swift
    let arr7 = [3,6,1,9,4,8]

    let sortedArr7 = arr7.sorted()
    print(sortedArr7[1])
```




## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values** √

Input: `[nil, "We", "come", nil, "in", "peace"]`
Output: `["We", "come", "in", "peace"]`

```swift
    let input1: [String?] = [nil, "We", "come", nil, "in", "peace"]
    var output1: [String] = []
    
    for word in input1 {
        if let word = word {
            output1.append(word)
        }
    }
    print(output1)
```

2. **Given an array of type [String?]? return an array of [String] removing all nil values** √

Input: `nil`

Output: `[]`

```swift

```

3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.** [ SKIPPED ]

Input: `[4, nil, 9, 5, nil]`

```swift
    let input3: [Int?] = [4, nil, 9, 5, nil]
    var sum = 0

    for number in input3 {
        
    //    if let result = number {
    //        guard number != nil
    //    }
    //
    }
```

Output: `18`

4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.** SKIPPED

Input: `nil`

Output: `0`

```swift

```

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`

```swift
    let input5: [Int?] = [1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3]
    var output = [Int]()

    for number in input5 {
        if let numberx = number {
            output.append(numberx)
        }
    }
    print(output.filter{$0 != 1}.reduce(0,+))
```

## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`

```swift
    let input = ["apple", "apple", "banana", "banana", "banana", "cake", "cake"]
    let inputSet = Set(input)
    print(inputSet)
```

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t`

```swift
let quote = "Never trust a computer you can't throw out a window ~ Steve Wozniak"

var letterFrequency = [String:Int]()

for letter in quote.lowercased().filter({$0 != " "}) {
    if let count = letterFrequency[String(letter)] {
        letterFrequency[String(letter)] = count + 1
    } else {
        letterFrequency[String(letter)] = 1
    }
}

var highestFreq = 0
var highestLetter = (String)()

for (key,value) in letterFrequency {
    if value > highestFreq {
        highestFreq = value
        highestLetter = key
    }
}

print(highestLetter)
```

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice** √

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`

```swift 
let arr6 = [1,1,2,3,3,3,4,5,6,6,7]
var frequencyDict: [Int:Int] = [:]

for num in arr6 {
    if let count = frequencyDict[num] {
        frequencyDict[num] = count + 1
    } else {
        frequencyDict[num] = 1
    }
}

var appearsTwice = [Int]()

for (key, value) in frequencyDict {
    if value >= 2 {
        appearsTwice.append(key)
    }
}

print(appearsTwice)

```

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`

```swift
    let quote = "Never trust a computer you can't throw out a window ~ Steve Wozniak"

    var letterFrequency = [String:Int]()

    for letter in quote.lowercased().filter({$0 != " "}) {
        if let count = letterFrequency[String(letter)] {
            letterFrequency[String(letter)] = count + 1
        } else {
            letterFrequency[String(letter)] = 1
        }
    }

    var maxvalue = 0
    var secondmaxletter = ""
    var secondmaxcount = 0

    print(letterFrequency)

    for (key,value) in letterFrequency {
        
        if value > maxvalue {
            maxvalue = value
        } else if value > secondmaxcount && secondmaxcount < maxvalue {
            secondmaxcount = value
            secondmaxletter = key
        }
    }
    print(secondmaxletter)
```





## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`

```swift
let input = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

let out = input.sorted{$0 < $1}

print(out)
```

2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`

```swift
let input2 = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

let output2 = input.sorted{$0.count < $1.count}

print(output2)
```

3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`

```swift
let input3 = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

let output3 = input3.filter({$0.count >= 4})

print(output3)
```

4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`

```swift
    let quote = "Never trust a computer you can't throw out a window ~ Steve Wozniak"

    var letterFrequency = [String:Int]()

    for letter in quote.lowercased().filter({$0 != " "}) {
        if let count = letterFrequency[String(letter)] {
            letterFrequency[String(letter)] = count + 1
        } else {
            letterFrequency[String(letter)] = 1
        }
    }

    var maxvalue = 0
    var secondmaxletter = ""
    var secondmaxcount = 0

    print(letterFrequency)

    for (key,value) in letterFrequency {
        
        if value > maxvalue {
            maxvalue = value
        } else if value > secondmaxcount && secondmaxcount < maxvalue {
            secondmaxcount = value
            secondmaxletter = key
        }
    }
    print(secondmaxletter)
```

## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
    let number = [1,2,3,4,5,6]
    enum NumberType {
        case even        
        case odd
        
        func evenOrOdd(arr: [Int]) -> [Int] {
            var numArr: [Int] = [] 
            
            switch self { 
            
            case .even: 
                for numbers in arr {
                    if numbers % 2 == 0 {
                        numArr.append(numbers)
                    }
                }
                
            case .odd:
                for numbers in arr {
                    if numbers % 2 != 0 {
                        numArr.append(numbers)
                    }
                }
            }
            return numArr
        }
    }
    let even = NumberType.even
    print(even.evenOrOdd(arr: number))
```

Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`

2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
    let input2Enums = "Design is not just what it looks like and feels like. Design is how it works"

    enum StringType {
        case lowercase
        case uppercase
        
        func lowerOrUpper(_ str:String) -> String {
            
            switch self {
                
            case .lowercase:
                return str.lowercased()
                
            case .uppercase:
                return str.uppercased()
            }
        }
    }

    let uppercase = StringType.uppercase
    print(uppercase.lowerOrUpper(input2Enums))
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``

3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`
