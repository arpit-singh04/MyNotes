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
   
  ### WildCard Period
  - ```
    let text = "Making a cake"
    ```
    - the '.' character is used to represent a wildcard character which could be any possible character
    - however, note that the period will only replace one character and not multiple characters
    - multiple periods can be used to enhance search
    - ```
      let regex = /.ak./ig
      let res = text.match(regex)
      ```
    - ```out: ["Maki", "cake"]```
    - as seen, the period does not substitute the entire left over word, but only a single character which is why we only get "Maki", instead of "Making"

  ### Character Set []
  - ```
    let text1 = "big"
    let text2 = "pig"
    let text2 = "wig"
    ```
    - character set allows to define a set of potential wildcards characters and match with any one of them
    - for example ```let regex = /[bpw]ig/``` and then a testing the regex with any of the three texts will result in true as each text contains one of the characters in the character set as their first character
    - ```let text = "big, pig"``` - now we can use match function with the above regex which will tell us that "big" and "pig" exist in the string but not wig.

  - Note:
    - For a range of letters, say a-f or d-x, you can do a ```let regex = /[a-f]mber/``` instead of typing all letters from a to f.
    - Same is valid for range of numbers by using, say: ```let regex = /[2-8]mber/```
    - finally , numbers and letters can be combined and either will be allowed as wild card character: ```let regex = /[3-5m-s]ango/``` 
      
