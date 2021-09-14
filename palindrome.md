# Specification

Given a string, output true if it is a palindrome. False otherwise.

`racecar -> true`

# Solution

```java
boolean isPalindrome(String subject) {
  IntPredicate predicate = i -> subject.charAt(i) == subject.charAt(subject.length() - 1 - i);
  return IntStream.range(0, subject.length() / 2).takeWhile(predicate).count() == subject.length() / 2;
}
```