# Specification

Given a list of numbers, return the min and max numbers in a single iteration.

# Solution

```java
record MinAndMax(int min, int max) {}
MinAndMax minAndMax(List<Integer> numbers) {
  return numbers.stream()
    .reduce(
      new MinAndMax(MAX_VALUE, MIN_VALUE),
      (accumulator, i) -> {
        int currentMin = i < accumulator.min ? i : accumulator.min;
        int currentMax = i > accumulator.max ? i : accumulator.max;
        return new MinAndMax(currentMin, currentMax);
      },
      (ignored1, ignored2) -> null
  );
}
```