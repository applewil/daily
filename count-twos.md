# Specification

Given a number n, output the number of twos that appear in all the numbers between 0 and n (inclusive)

`25 -> 9`

# Solution

```java
int countTwos(int n) {
  return (int) Stream.iterate(0, i -> i < Math.log10(n), i -> i + 1)
      .map(i -> n / Math.pow(10, i) % 10)
      .filter(digit -> digit.intValue() == 2)
      .count();
}

int countTwosInRange(int end) {
  return Stream.iterate(0, i -> i <= end, i -> i + 1).mapToInt(Integer::intValue).map(this::countTwos).sum();
}
```