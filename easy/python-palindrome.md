 
 # Is Palindrome (Python)
### DataLemur Easy Challenge

Below are my completed solutions to SQL challenges on [DataLemur](https://datalemur.com/).

This page serves as a portfolio of my skills in solving business problems using advanced query techniques.

### Is Palindrome (Python)
* **Description:** Checks whether a string is palindrom.
* **Approach:** Comparing list length and set length.
* **Links:** [Problem Link](https://datalemur.com/questions/python-palindrome)


### SQL Query
```

def isPalindrome(phrase):
  lft = 0
  rgt = len(phrase)-1
  palin = True
  while (lft <= rgt) and palin:
      # print("lft",phrase[lft])
      while not phrase[lft].isalnum():
        lft += 1
      # print("rgt",phrase[rgt])
      while not phrase[rgt].isalnum():
        rgt -= 1
      # print("lft-rgt",lft,rgt, phrase[lft], phrase[rgt])
        
      if phrase[lft].lower() == phrase[rgt].lower():
        lft += 1
        rgt -= 1
      else:
        palin = False
  return palin
  

```

[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)

[My Upwork Profile](https://upwork.com/freelancers/eriyawane)
[My Freelancer Profile](https://www.freelancer.com/u/erimilis)




