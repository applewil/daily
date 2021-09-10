# Specification

Given a list of numbers, output all the distinct pairs that add up to 7.

`[ 3, 4, 5, 6, 7, 8, 0, 100, -93, -1] -> Pair[a=3, b=4], Pair[a=7, b=0], Pair[a=8, b=-1], Pair[a=100, b=-93]`

# Solution

```java
record Pair(Integer a, Integer b) {}

List<Pair> sumPairs(int sum, List<Integer> numbers) {
  var map = new HashMap<Integer, Integer>();
  numbers.forEach(i -> map.put(sum - i, i));
  return numbers.stream()
      .filter(map::containsKey)
      .peek(i -> map.remove(sum - i)) // remove the compliment to avoid duplicates
      .map(i -> new Pair(i, sum - i))
      .toList();
}
```