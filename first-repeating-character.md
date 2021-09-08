# Specification

Given a string, output the first character that occurs multiple times.

`abba -> b`

# Solution

```java
OptionalInt firstRepeating(String subject) {
  Set<Integer> visited = new HashSet<>();
  return subject.chars()
    .dropWhile((character) -> {
      Boolean isFirstOccurance = !visited.contains(character);
      visited.add(character);
      return isFirstOccurance;
    })
    .findFirst();
}
```