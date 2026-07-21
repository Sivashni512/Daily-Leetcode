# Find Duplicate Elements in an Array using HashSet

## 📌 Problem Statement
Write a Java program to find duplicate elements in an integer array using a **HashSet**.

---

## 🧩 Algorithm
1. Create a **HashSet** to store unique elements.  
2. Create another **HashSet** to store duplicate elements.  
3. Traverse the array one element at a time.  
4. If an element is already present in the first HashSet, add it to the duplicate set.  
5. Otherwise, add it to the first HashSet.  
6. Display all duplicate elements.

---

## 💻 Java Program
```java
import java.util.HashSet;

public class FindDuplicates {
    public static void main(String[] args) {

        int[] arr = {2, 5, 3, 2, 8, 5, 9, 1, 3};

        HashSet<Integer> unique = new HashSet<>();
        HashSet<Integer> duplicates = new HashSet<>();

        for (int num : arr) {
            if (!unique.add(num)) {
                duplicates.add(num);
            }
        }

        System.out.println("Duplicate Elements: " + duplicates);
    }
}
