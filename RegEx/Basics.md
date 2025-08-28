Will be using javascript examples - but usually applicable across languages with small changes

## Basic Regex Representation, test function and flags
  ### Basics
  - ```
    let sentence = "Hello GitHub, what a normal day it is, isn't it?"
    let regex = /it/
    ```
    - The string that needs to be searched goes in between /[here]/
    - Test the existence of the string with ```regex.test(sentence)``` which returns a boolean value. Note that regex is case sensitive by default so testing "b" with "B" will result in false
    - Test the existence of the string while ignoring the case of the seached string using the i flag (case insensitive flag)
      - ```
        let regex = /it/i
        regex.test(sentence)
        ```
    - Note that test returns true as soon as it finds a search hit and stops looking for more
    - Note that flag goes after the second '/' and can be stacked, so later when using both i and g, simply write ```/it/ig```
    
  ### OR Operator
  - When we have to ensure that one out of multiple strings exists in a larger string
  - ```
    let regex = /burger|pizza|cake/i
    regex.test(sentence)
    ```
    - This will return true for ```sentence = "I love pizza"```
    - This will also return true for ```sentence = "I love BUrgEr"```

  ### match() function
  - used to match a regexliteral to a string - kind of like test, but we can look for occurence indexes with this
  - ```
    let text = "The white cat and the black cat"
    ```
  - match() without g flag: ```let regex = /cat/```
    - if we do ```text.match(regex)``` it will return an object with multiple fields like index of first occurence, the original string and such
  - match() with the g flag ```let regex = /cat/g```
    - this returns an array with all the matches without any index or original string. ```out: ["cat", "cat"]```
    - however you can use the array and find it's length to check the number of times the match occured in the string
      
