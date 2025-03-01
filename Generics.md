# Generics

Created: February 16, 2025 2:18 PM

### **Generics in Java - Detailed Explanation**

Java Generics is a powerful feature that allows you to write **type-safe** and **reusable** code by introducing **parameterized types**. Generics were introduced in **Java 5** and primarily used in **classes, interfaces, and methods** to specify the type at compile-time rather than using `Object` and performing explicit type casting.

---

## **1. What Are Generics?**

Generics allow defining **classes, interfaces, and methods** with **type parameters**. These parameters act as placeholders for actual types and are specified when an object is instantiated or a method is called.

### **Example Without Generics (Before Java 5)**

```java
class Box {
    private Object value;

    public void set(Object value) {
        this.value = value;
    }

    public Object get() {
        return value;
    }
}

public class Main {
    public static void main(String[] args) {
        Box box = new Box();
        box.set("Hello"); // Storing a String

        String str = (String) box.get(); // Explicit type casting
        System.out.println(str);
    }
}

```

**Problems with this approach:**

- **Type Safety Issue**: You can store any type in `Box`, leading to runtime errors.
- **Explicit Casting Required**: You must manually cast the object when retrieving it, which may cause `ClassCastException`.

---

## **1. Introduction to Generics**

✅ Generics allow **type safety** and **code reusability**.

✅ Introduced in **Java 5** to eliminate type casting and `ClassCastException`.

✅ Enables defining **classes, interfaces, and methods** with **type parameters**.

---

## **2. Generic Class**

✅ A class that operates on **parameterized types**.

✅ **Syntax:**

```java
class Box<T> {
    private T value;
    public void set(T value) { this.value = value; }
    public T get() { return value; }
}

```

✅ **Example Usage:**

```java
Box<String> stringBox = new Box<>();
stringBox.set("Hello");
String str = stringBox.get();  // No casting required

```

---

## **3. Generic Methods**

✅ Allows defining **methods with type parameters**.

✅ **Syntax:**

```java
class Util {
    public static <T> void print(T item) {
        System.out.println(item);
    }
}

```

✅ **Example Usage:**

```java
Util.print(10);      // Works with Integer
Util.print("Hello"); // Works with String

```

---

## **4. Bounded Type Parameters**

✅ Restricts type parameters to a specific class hierarchy using `extends`.

✅ **Syntax:**

```java
class Data<T extends Number> { }

```

✅ **Example Usage:**

```java
class MathOperations<T extends Number> {
    public double square(T num) {
        return num.doubleValue() * num.doubleValue();
    }
}

```

✅ `T extends Number` ensures **only numerical types** (`Integer`, `Double`, etc.) are allowed.

---

## **5. Wildcards in Generics**

✅ Used when the exact type is **unknown or flexible**.

| Wildcard Type | Meaning |
| --- | --- |
| `<?>` | Any type (Unbounded) |
| `<? extends T>` | T or any subclass of T (Upper Bounded) |
| `<? super T>` | T or any superclass of T (Lower Bounded) |

✅ **Examples:**

1. **Unbounded Wildcard (`<?>`)** – Accepts any type:
    
    ```java
    public static void printList(List<?> list) { }
    
    ```
    
2. **Upper Bounded Wildcard (`<? extends Number>`)** – Accepts `Number` or its subclasses:
    
    ```java
    public static double sum(List<? extends Number> list) { }
    
    ```
    
3. **Lower Bounded Wildcard (`<? super Integer>`)** – Accepts `Integer` or its superclasses:
    
    ```java
    public static void addNumber(List<? super Integer> list) { }
    
    ```
    

---

## **6. Type Erasure (How Generics Work Internally)**

✅ Generics exist **only at compile-time**, and **type parameters are removed** at runtime.

✅ The compiler replaces type parameters with **Object** (or the first bounded type).

✅ **Example:**

```java
class Box<T> { T value; }

```

After **type erasure**, it becomes:

```java
class Box { Object value; }

```

---

## **7. Limitations of Generics**

❌ **Cannot use primitive types (`int`, `double`) directly.**

✅ Use wrapper classes (`Integer`, `Double`).

❌ **Cannot create generic arrays.**

```java
T[] arr = new T[10];  // Not allowed

```

✅ Use `List<T>` instead.

---

## **8. Advantages of Generics**

✔ **Type Safety** – Prevents `ClassCastException`.

✔ **Code Reusability** – Same code works for different types.

✔ **Eliminates Type Casting** – No need for explicit casting.

---

## **9. Generic Interfaces**

✅ Interfaces can also be generic.

✅ **Syntax:**

```java
interface Container<T> {
    void add(T item);
    T retrieve();
}

```

✅ **Example Implementation:**

```java
class DataStore<T> implements Container<T> {
    private T data;
    public void add(T item) { this.data = item; }
    public T retrieve() { return data; }
}

```

---

## **10. Critical and Tricky Interview Questions on Generics**

### **Q1. Can you create an array of generics in Java?**

❌ **No, Java does not allow generic arrays.**

✅ **Solution:** Use `List<T>` instead.

```java
// Not allowed:
T[] arr = new T[10];

// Allowed:
List<T> list = new ArrayList<>();

```

---

### **Q2. What is Type Erasure in Java Generics?**

✅ **Type Erasure removes generic type information at runtime.**

✅ **Example:**

```java
class Box<T> { T value; } // At compile-time

```

⬇ **After Erasure:**

```java
class Box { Object value; } // At runtime

```

---

### **Q3. Can we use `instanceof` with Generics?**

❌ **No, because generic type information is erased at runtime.**

| Scenario | Works? | Reason |
| --- | --- | --- |
| `obj instanceof T` | ❌ No | `T` is erased at runtime. |
| `obj instanceof Box<?>` | ✅ Yes | `Box<?>` is a known class at runtime. |
| `clazz.isInstance(obj)` | ✅ Yes | `Class<T>` retains type info at runtime. |

✅ **Workaround:**

```java
if (obj instanceof Box<?>) { // Allowed
    System.out.println("It's a Box!");
}

```

---

### **Q4. Can we create a static field of a generic type?**

❌ **No, because generics are resolved at compile-time, and static fields are shared among all instances.**

✅ **Example:**

```java
class Test<T> {
    static T data; // ❌ Not allowed
}

```

## ✅ **Solution:** Use a non-static field instead.

### **Q5. What is the difference between `? extends T` and `? super T`?**

| Wildcard | Meaning | Example |
| --- | --- | --- |
| `? extends T` | Accepts `T` or its subclasses | `List<? extends Number>` accepts `Integer`, `Double` |
| `? super T` | Accepts `T` or its superclasses | `List<? super Integer>` accepts `Integer`, `Number`, `Object` |

---

### **Q6. What is the difference between Generics and Object?**

| Feature | Generics | Object |
| --- | --- | --- |
| Type Safety | ✅ Type-safe | ❌ Type casting needed |
| Compile-time Check | ✅ Yes | ❌ No |
| Performance | ✅ Faster (avoids unnecessary casting) | ❌ Slower |

---

### **Q7. Can we create an instance (object)of a type parameter (`T`) in Generics?**

❌ **No, because Java does not know what `T` will be at runtime.**

✅ **Solution:** Use reflection or factory methods.

```java
class Test<T> {
    T obj;
    public Test(Class<T> clazz) throws Exception {
        obj = clazz.getDeclaredConstructor().newInstance();
    }
}

```

---

### **Q8. Can Generics be used with Enums?**

✅ **Yes, you can use Generics with Enums.**

```java
enum Color { RED, GREEN, BLUE; }

class EnumHolder<T extends Enum<T>> {
    T color;
    public EnumHolder(T color) { this.color = color; }
}

```

---

## **Conclusion**

✔ **Generics improve code safety and flexibility.**

✔ **Wildcard types (`?`) help with unknown type scenarios.**

✔ **Bounded types (`extends`, `super`) restrict generic parameters.**

✔ **Type erasure removes generics at runtime for backward compatibility.**

Would you like real-world examples of **Generics in large-scale applications**? 🚀