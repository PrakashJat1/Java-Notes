# Arrays and Collections class

Created: February 14, 2025 9:37 PM

### **1. Sorting Methods**

```java

static void sort(int[] a)
static void sort(int[] a, int fromIndex, int toIndex)
static void sort(Object[] a)
static void sort(Object[] a, int fromIndex, int toIndex)
static <T> void sort(T[] a, Comparator<? super T> c)
static <T> void sort(T[] a, int fromIndex, int toIndex, Comparator<? super T> c)
```

---

### **2. Searching Methods**

```java

static int binarySearch(int[] a, int key)
static int binarySearch(int[] a, int fromIndex, int toIndex, int key)
static int binarySearch(Object[] a, Object key)
static <T> int binarySearch(T[] a, T key, Comparator<? super T> c)
```

---

### **3. Comparison Method**

```java

static boolean equals(int[] a, int[] a2)
static boolean equals(Object[] a, Object[] a2)
static boolean deepEquals(Object[] a1, Object[] a2)//for multidimensional Array
```

---

### **4. Filling Method**

```java

static void fill(int[] a, int val)
static void fill(int[] a, int fromIndex, int toIndex, int val)
static void fill(Object[] a, Object val)
static void fill(Object[] a, int fromIndex, int toIndex, Object val)
```

---

### **5. Conversion Methods**

```java

static String toString(int[] a)
static String toString(Object[] a)
static String deepToString(Object[] a)

//Hashing
static int hashCode(Object[] a)
static int deepHashCode(Object[] a)
```

---

### **6. Copying Methods**

```java

static int[] copyOf(int[] original, int newLength)
static <T> T[] copyOf(T[] original, int newLength)

static int[] copyOfRange(int[] original, int from, int to)
static <T> T[] copyOfRange(T[] original, int from, int to)
```

---

### **7. Miscellaneous Methods**

```java
static <T> List<T> asList(T... a)
static void parallelSort(byte[] a)
static void parallelSort(byte[] a, int fromIndex, int toIndex)
static void parallelSort(char[] a)
static void parallelSort(char[] a, int fromIndex, int toIndex)
static void parallelSort(double[] a)
static void parallelSort(double[] a, int fromIndex, int toIndex)
static void parallelSort(float[] a)
static void parallelSort(float[] a, int fromIndex, int toIndex)
static void parallelSort(int[] a)
static void parallelSort(int[] a, int fromIndex, int toIndex)
static void parallelSort(long[] a)
static void parallelSort(long[] a, int fromIndex, int toIndex)
static void parallelSort(short[] a)
static void parallelSort(short[] a, int fromIndex, int toIndex)
static <T> void parallelSort(T[] a, Comparator<? super T> cmp)
static <T> void parallelSort(T[] a, int fromIndex, int toIndex, Comparator<? super T> cmp)
static void parallelPrefix(int[] array, IntBinaryOperator op)
static void parallelPrefix(long[] array, LongBinaryOperator op)
static void parallelPrefix(double[] array, DoubleBinaryOperator op)
static <T> void parallelPrefix(T[] array, BinaryOperator<T> op)
static Spliterator.OfInt spliterator(int[] array)
static Spliterator.OfInt spliterator(int[] array, int startInclusive, int endExclusive)
static Spliterator.OfLong spliterator(long[] array)
static Spliterator.OfLong spliterator(long[] array, int startInclusive, int endExclusive)
static Spliterator.OfDouble spliterator(double[] array)
static Spliterator.OfDouble spliterator(double[] array, int startInclusive, int endExclusive)
static <T> Spliterator<T> spliterator(T[] array)
static <T> Spliterator<T> spliterator(T[] array, int startInclusive, int endExclusive)
static IntStream stream(int[] array)
static IntStream stream(int[] array, int startInclusive, int endExclusive)
static LongStream stream(long[] array)
static LongStream stream(long[] array, int startInclusive, int endExclusive)
static DoubleStream stream(double[] array)
static DoubleStream stream(double[] array, int startInclusive, int endExclusive)
static <T> Stream<T> stream(T[] array)
static <T> Stream<T> stream(T[] array, int startInclusive, int endExclusive)
```

## **📌**Collections Methods

| **Method** | **Use Case** |  |
| --- | --- | --- |
| `sort()` | Sorting algorithms (quick sort, merge sort, etc.) |  |
| `binarySearch()` | Searching algorithms (binary search) |  |
| `frequency()` | Counting occurrences of an element |  |
| `max() / min()` | Finding largest/smallest element |  |
| `reverse()` | Reversing elements (useful for two-pointer approach) |  |
| `rotate()` | Circular shifting |  |
| `shuffle()` | Randomizing order (useful for randomized algorithms) |  |
| `swap()` | Swapping elements (useful in sorting) |  |
| `unmodifiableList()` | Making a collection read-only |  |
| `disjoint()` | Checking if two sets are disjoint |  |
| `isEmpty()` | Edge case handling |  |

## **1. Sorting Methods (Useful for Sorting Algorithms)**

```java

static <T extends Comparable<? super T>> void sort(List<T> list)
static <T> void sort(List<T> list, Comparator<? super T> c)
```

✅ **Usage:** Sorts a list in **ascending order** (natural order) or **custom order** using a comparator.

🔹 **Example:**

```java

List<Integer> list = Arrays.asList(5, 2, 9, 1, 3);
Collections.sort(list);
System.out.println(list); // Output: [1, 2, 3, 5, 9]
```

---

## **2. Searching Methods (Useful for Searching Algorithms)**

```java
j
static <T> int binarySearch(List<? extends Comparable<? super T>> list, T key)
static <T> int binarySearch(List<? extends T> list, T key, Comparator<? super T> c)
```

✅ **Usage:** Uses **binary search** to find an element (works only on **sorted lists**).

🔹 **Example:**

```java

List<Integer> list = Arrays.asList(1, 2, 3, 5, 9);
int index = Collections.binarySearch(list, 5);
System.out.println(index); // Output: 3 (index of 5 in sorted list)
```

---

## **3. Frequency Check (Useful for Counting Occurrences)**

```java

static int frequency(Collection<?> c, Object o)
```

✅ **Usage:** Returns **count of occurrences** of an element in a collection.

🔹 **Example:**

```java
List<Integer> list = Arrays.asList(1, 2, 3, 2, 2, 5, 3);
int count = Collections.frequency(list, 2);
System.out.println(count); // Output: 3
```

---

## **4. Maximum & Minimum Elements (Useful for Finding Extrema)**

```java

static <T extends Object & Comparable<? super T>> T max(Collection<? extends T> coll)
static <T extends Object & Comparable<? super T>> T min(Collection<? extends T> coll)
```

✅ **Usage:** Finds the **largest** or **smallest** element in a collection.

🔹 **Example:**

```java

List<Integer> list = Arrays.asList(10, 20, 5, 8, 30);
int max = Collections.max(list);
int min = Collections.min(list);
System.out.println("Max: " + max + ", Min: " + min); // Output: Max: 30, Min: 5
```

---

## **5. Reverse a List (Useful for Reverse Order Traversal)**

```java

static void reverse(List<?> list)
```

✅ **Usage:** Reverses the elements of a list **in-place**.

🔹 **Example:**

```java

List<Integer> list = Arrays.asList(1, 2, 3, 4, 5);
Collections.reverse(list);
System.out.println(list); // Output: [5, 4, 3, 2, 1]
```

---

## **6. Rotate a List (Useful for Circular Rotations)**

```java

static void rotate(List<?> list, int distance)
```

✅ **Usage:** Rotates a list by shifting elements by `distance` positions.

🔹 **Example:**

```java

List<Integer> list = Arrays.asList(1, 2, 3, 4, 5);
Collections.rotate(list, 2);
System.out.println(list); // Output: [4, 5, 1, 2, 3]
```

---

## **7. Shuffle a List (Useful for Randomizing Elements)**

```java

static void shuffle(List<?> list)
static void shuffle(List<?> list, Random rnd)
```

✅ **Usage:** Shuffles a list randomly.

🔹 **Example:**

```java

List<Integer> list = Arrays.asList(1, 2, 3, 4, 5);
Collections.shuffle(list);
System.out.println(list); // Output: Randomized order (e.g., [3, 1, 5, 2, 4])
```

---

## **8. Swapping Elements in a List (Useful for Sorting Algorithms)**

```java

static void swap(List<?> list, int i, int j)
```

✅ **Usage:** Swaps two elements in a list.

🔹 **Example:**

```java

List<Integer> list = Arrays.asList(1, 2, 3, 4, 5);
Collections.swap(list, 1, 3);
System.out.println(list); // Output: [1, 4, 3, 2, 5]
```

---

## **9. Unmodifiable Collections (Useful for Making Immutable Data)**

```java

static <T> List<T> unmodifiableList(List<? extends T> list)
static <T> Set<T> unmodifiableSet(Set<? extends T> s)
static <T> Map<K,V> unmodifiableMap(Map<? extends K, ? extends V> m)
```

✅ **Usage:** Creates **read-only** collections (cannot be modified after creation).

🔹 **Example:**

```java

List<Integer> list = Collections.unmodifiableList(Arrays.asList(1, 2, 3));
list.add(4); // Throws UnsupportedOperationException
```

---

## **10. Creating Singleton Collections (Useful for Special Cases)**

```java
java
CopyEdit
static <T> List<T> singletonList(T o)
static <T> Set<T> singleton(T o)
static <K,V> Map<K,V> singletonMap(K key, V value)

```

✅ **Usage:** Creates a collection **with only one elements**

🔹 **Example:**

```java
List<Integer> singleList = Collections.singletonList(42);
System.out.println(singleList); // Output: [42]
```

---

## **11. Disjoint Method (Check if Two Collections Have No Common Elements)**

```java

static boolean disjoint(Collection<?> c1, Collection<?> c2);
```

✅ **Usage:** Returns `true` if **two collections have no common elements**.

🔹 **Example:**

```java

List<Integer> list1 = Arrays.asList(1, 2, 3);
List<Integer> list2 = Arrays.asList(4, 5, 6);
boolean result = Collections.disjoint(list1, list2);
System.out.println(result); // Output: true

```

---

## **12. Checking if a Collection is Empty (Useful for Edge Cases in DSA)**

```java

static boolean isEmpty(Collection<?> c)
```

✅ **Usage:** Checks whether a collection is **empty**.

🔹 **Example:**

```java

List<Integer> list = new ArrayList<>();
System.out.println(Collections.isEmpty(list)); // Output: true

```