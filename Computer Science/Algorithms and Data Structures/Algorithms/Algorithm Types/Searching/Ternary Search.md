

**Summary:**
Ternary Search is a searching algorithm designed to find the position of a target value within a sorted array. It divides the array into three parts and narrows down the search range by comparing the target value with the elements at the one-third and two-thirds positions. Ternary Search is best suited for scenarios where the array is sorted and the target value can be found within a limited range.

**Algorithm:**

1. Divide the search range into three parts.
2. Compare the target value with the elements at one-third and two-thirds positions.
3. Based on the comparison, narrow down the search range to the appropriate one-third of the array.
4. Repeat steps 1-3 until the target value is found or the search range becomes empty.

**Code (Java):**

```java
public class TernarySearch {
    public static int ternarySearch(int[] arr, int x) {
        int left = 0;
        int right = arr.length - 1;

        while (left <= right) {
            int mid1 = left + (right - left) / 3;
            int mid2 = right - (right - left) / 3;

            if (arr[mid1] == x)
                return mid1;
            if (arr[mid2] == x)
                return mid2;

            if (x < arr[mid1])
                right = mid1 - 1;
            else if (x > arr[mid2])
                left = mid2 + 1;
            else {
                left = mid1 + 1;
                right = mid2 - 1;
            }
        }

        return -1; // Element not found
    }

    public static void main(String[] args) {
        int[] arr = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
        int x = 6;
        int index = ternarySearch(arr, x);
        if (index != -1)
            System.out.println("Element found at index " + index);
        else
            System.out.println("Element not found");
    }
}
```

**Complexity:**
- **Time Complexity:** O(log3 n), where n is the number of elements in the array.
- **Space Complexity:** O(1).

**Advantages:**
1. Efficient for searching in sorted arrays.
2. Guarantees logarithmic time complexity.
3. Performs better than binary search for larger arrays with a limited search range.
4. Requires fewer comparisons than binary search.

**Disadvantages:**
1. Requires the array to be sorted.
2. May not perform well for very small arrays or arrays with irregular distribution.
3. Not suitable for unbounded or unknown array sizes.

**Applications:**
1. Searching in sorted arrays with a limited search range.
2. Finding elements within a known interval or range.
3. Where binary search may have high overhead or complexity.