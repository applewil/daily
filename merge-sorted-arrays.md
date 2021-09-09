# Specification

Given two sorted arrays A and B, merge B into A. Assume array A has exactly enough space to hold it's own elements and Array B's elements.

```
A = [1, 3, 5, 6, 0, 0, 0] 
B = [2, 4, 7] 
-> 
[1, 2, 3, 4, 5, 6, 7]
```

# Solution

```java
void reorderFirstElements(int[] array) {
  if (array.length > 1 && array[0] > array[1]) {
    var temp = array[0];
    array[0] = array[1];
    array[1] = temp;
  }
}

void mergeSortedArrays(int lengthOfA, int[] a, int[] b) {
  var i = 0;
  for (; i < lengthOfA; i++) {
    if (a[i] > b[0]) {
      var temp = a[i];
      a[i] = b[0];
      b[0] = temp;
      reorderFirstElements(b);
    }
  }
  for (; i < a.length; i++) {
    a[i] = b[i - lengthOfA];
  }
}
```
