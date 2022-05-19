# Swift Coding Challenges
> Click ⭐if you like the project. Pull Requests are highly appreciated. Follow me @faisalkarimi for technical updates.
---

**Challenges**

| [Challenge 1](#challenge-1) | [Challenge 2](#challenge-2) | [Challenge 3](#challenge-3) | [Challenge 4](#challenge-4) | [Challenge 5](#challenge-5) |[Challenge 6](#challenge-6) | [Challenge 7](#challenge-7) | [Challenge 8](#challenge-8) | [Challenge 9](#challenge-9) | [Challenge 10](#challenge-10)
| [Challenge 11](#challenge-11) |

#### **Challenge 1:**

Q. Given a string of characters, return a substring of unique characters?

**Solution:**

```swift
//Takes a string as argument and returns only unique characters in the string
func uniqueCharactersInString(_ str: String) -> String {
    var uniqueString = ""
    uniqueString = str.reduce(uniqueString, { (result, char) in
        if result.contains(char) {
            return result
        } else {
            return result + String.init(char)
        }
    })
    return uniqueString
}

```
**Usage:**

```swift
var myString = "This is my sample note"
let result = uniqueCharactersInString(myString)
print(result) //Output: This myaplenot
```

#### **Challenge 2:**

Q. Write a function to compare if arms of two individuals are equally strong?

**Solution:**

```swift
    //Takes two dictionaries as arguments and returns only true or false
func areEquallyStrong(personOne: Dictionary<String, Int>, personTwo: Dictionary<String, Int>) -> Bool {
    let leftArmPersonOne = personOne["left"]
    let rightArmPersonOne = personOne["right"]
    let leftArmPersonTwo = personTwo["left"]
    let rightArmPersonTwo = personOne["right"]
    
    if leftArmPersonOne == leftArmPersonTwo ||
        leftArmPersonOne == rightArmPersonOne &&
        rightArmPersonOne == leftArmPersonTwo ||
        rightArmPersonOne == rightArmPersonTwo {
        return true
    } else {
        return false
    }
}
```
**Usage:**

```swift
    let myArm = ["left": 15, "right": 10]
    let myFriendsArm = ["left": 10, "right": 15]

    print(areEquallyStrong(personOne: myArm, personTwo: myFriendsArm))
```

#### **Challenge 3:**

Q. Write a function to determine if two arrays are similar?

**Solution:**

```swift
    //Takes two arrays as arguments and returns only true or false
func isSimilar(arrayOne: [Int], arrayTwo: [Int]) -> Bool {
    if arrayOne.count != arrayTwo.count {
        return false
    }
    
    return sumUp(arrayOne) == sumUp(arrayTwo)
}

func sumUp(_ array: [Int]) -> Int {
    return array.reduce(0) { acc, cur in
        acc + cur
    }
}
```
**Usage:**

```swift
let arr1 = [1,2,2]
let arr2 = [2,1,2]

print(isSimilar(arrayOne: arr1, arrayTwo: arr2))
```
#### **Challenge 4:**

Q. Write a function to perform replace all operation in an array?

**Solution:**

```swift
    //Takes an array, a search term and a replacement number & will return an array
func replaceAll(_ array: [Int], term: Int, with: Int) -> [Int] {
    return array.map { eachItem in
        eachItem == term ? with : eachItem
    }
}
```
**Usage:**

```swift
var myArray = [1,2,3,1,2]

print(replaceAll(myArray, term: 1, with: 4)) // [4,2,3,4,2]
```

#### **Challenge 5:**

Q. Write a function to return the number of vowels in a sentence?

**Solution:**

```swift
    //Takes a string as argument and returns the total number of vowels in it.
func numberOfVowels(in aSentence: String) -> Int {
    let vowels = ["a", "e", "i", "o", "u"]
    var count = 0
    
    for char in aSentence.lowercased() {
        if vowels.contains(String(char)) {
            count += 1
        }
    }

    return count
}
```
**Usage:**

```swift
let myString = "I want to know the number of vowels in the sentence"

print(numberOfVowels(in: myString)) // 15
```

#### **Challenge 6:**

Q. Write a function to reverse a string?

**Solution:**

```swift
    //Takes a string as argument and returns the string in reversed order.
func reverseString(input: String) -> String {
    return input.reduce("") {
        "\($1)" + $0
    }
}
```
**Usage:**

```swift
let myStr = "Hello world!"

print(reverseString(input: myStr)) //!dlrow olleH
```

#### **Challenge 7:**

Q. Write a function to return the character with maximum occurance in a sentence?

**Solution:**

```swift
    //Takes a string as argument and returns the string with maximum occurances.
func mostRepeatedCharacter(in aSentence: String) -> String {
    var charMap = [String: Int]()
    
    for char in aSentence {
        charMap[String(char)] = (charMap[String(char)] ?? 0) + 1
    }
    
    let max = charMap.reduce(charMap.first!) { $1.value > $0.value ? $1 : $0 }
    
    return max.key
}
```
**Usage:**

```swift
let myStr = "Hello World"

print("Most repeated character is: \(mostRepeatedCharacter(in: myStr))") // Most repeated character is: l
```

#### **Challenge 8:**

Q. Write a function to capitalize first letter of each word in a sentence?

**Solution:**

```swift
    //Takes a string as argument and returns the same string with each words first letter capitalized.
func capitalizeEachLetter(in aSentence: String) -> String {
    return aSentence.capitalized
}
```
**Usage:**

```swift
let myStr = "hello world again"

print(capitalizeEachLetter(in: myStr)) // Hello World Again
```

#### **Challenge 9:**

Q. Write a function to determine if two sentences are anagram?
--
Note: An anagram is a word or phrase that's formed by rearranging the letters of another word or phrase.

**Solution:**

```swift
    //Takes two strings as arguments and returns a boolean
func isAnagram(sentenceA: String?, sentenceB: String?) -> Bool {
    if (sentenceA == nil || sentenceB == nil) || sentenceA?.count != sentenceB?.count {
        return false
    }
    var str1 = [String]()
    var str2 = [String]()
    
    for letter in sentenceA!.lowercased().sorted() {
        str1.append(String(letter))
    }
    
    for letter in sentenceB!.lowercased().sorted() {
        str2.append(String(letter))
    }
    
    return String(str1.joined()) == String(str2.joined())
}
```
**Usage:**

```swift
let str1 = "secure"
let str2 = "Rescue"

print(isAnagram(sentenceA: str1, sentenceB: str2)) //true
```

#### **Challenge 10:**

Q. Write a function to determine if two sentences are anagram?
--
Note: An anagram is a word or phrase that's formed by rearranging the letters of another word or phrase.

**Solution:**

```swift
    //Takes two strings as arguments and returns a boolean
func isAnagram(sentenceA: String?, sentenceB: String?) -> Bool {
    if (sentenceA == nil || sentenceB == nil) || sentenceA?.count != sentenceB?.count {
        return false
    }
    var str1 = [String]()
    var str2 = [String]()
    
    for letter in sentenceA!.lowercased().sorted() {
        str1.append(String(letter))
    }
    
    for letter in sentenceB!.lowercased().sorted() {
        str2.append(String(letter))
    }
    
    return String(str1.joined()) == String(str2.joined())
}
```
**Usage:**

```swift
let str1 = "secure"
let str2 = "Rescue"

print(isAnagram(sentenceA: str1, sentenceB: str2)) //true
```

#### **Challenge 11:**

Q. Write a function to determine if two words are palindromes?
--
Note: A palindrome is a word, sentence, verse, or even number that reads the same backward or forward.

**Solution:**

```swift
    //Takes a string as argument and returns a boolean
func isPalindrome(word: String) -> Bool {
    return word == String(word.reversed())
}
```
**Usage:**

```swift
let str = "civic"

print(isPalindrome(word: str)) //true
```
