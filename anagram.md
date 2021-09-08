# Specification

Given a string return true if it is an anagram. False otherwise.

# Solution

```java
boolean anagram(String subject) {
  char[] characters = subject.toCharArray();
  boolean isAnagram = true;
  for(int i=0;
      i < characters.length && isAnagram == true;
      isAnagram = characters[i] == characters[characters.length - 1 - i], i++);
  return isAnagram;
}
```