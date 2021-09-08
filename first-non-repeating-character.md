# Specification

Given a string, output the first character that does not appear multiple times.

`abca -> b`

# Solution

```java
OptionalInt firstNonRepeating(String subject) {
  Map<Integer, Integer> counts = new HashMap<>();
  subject.chars().forEach((character) -> {
    int count = counts.getOrDefault(character, 0);
    counts.put(character, count + 1);
  });
  return subject.chars()
    .dropWhile((character) -> counts.get(character) > 1)
    .findFirst();
}
```