# Specification

Given a string, return true if every character in the string is unique. False otherwise.

# Solution

```java
boolean heterogram(String subject) {
  return subject.chars().distinct().count() == subject.length();
}
```