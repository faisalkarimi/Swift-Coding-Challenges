# Swift Coding Challenges
> Click ⭐if you like the project. Pull Requests are highly appreciated. Follow me @faisalkarimi for technical updates.
---

**Challenge 1:**
1. Given a string of characters, return a substring of unique characters?
```swift
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

