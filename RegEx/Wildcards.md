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
