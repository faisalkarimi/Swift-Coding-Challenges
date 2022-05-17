# Swift Coding Challenges
> Click ⭐if you like the project. Pull Requests are highly appreciated. Follow me @faisalkarimi for technical updates.
---

**Challenge 1:**

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

**Challenge 2:**

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

**Challenge 3:**

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
