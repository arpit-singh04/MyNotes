Will be using javascript examples - but usually applicable across languages with small changes

## Basic Regex Representation, test function and flags
  ### Basics
  - ```
    let sentence = "Hello GitHub, what a normal day it is, isn't it?"
    let regex = /it/
    ```
    - The string that needs to be searched goes in beteween /[here]/
    - Test the existence of the string with ```regex.test(sentence)``` which returns a boolean value. Note that regex is case sensitive by default so testing "b" with "B" will result in false
    - Test the existence of the string while ignoring the case of the seached string using the i flag (case insensitive flag)
      - ```
        let regex = /it/i
        regex.test(sentence)
        ```
    - Note that test only looks for the first occurence of the searched string and ignores the rest
    - Note that flag goes after the second '/' and can be stacked, so later when using both i and g, simply write ```/it/ig```
    
  ### OR Operator
  - When we have to ensure that one out of multiple strings exists in a larger string
  - ```
    let regex = /burger/pizza/cake/i
    regex.test(sentence)
    ```
    - This will return true for ```sentence = "I love pizza"```
    - This will also return true for ```sentence = "I love BUrgEr"```
      
