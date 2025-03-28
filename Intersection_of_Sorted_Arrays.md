## **Intersection of Sorted Arrays**

### **Efficient Approach**
**Two-pointer technique** (since the arrays are sorted):  
- Traverse both arrays simultaneously.
- If elements are equal, add them to the result (avoiding duplicates).
- If an element in the first array is smaller, move its pointer forward.
- If an element in the second array is smaller, move its pointer forward.
   
---

### **Python Solution**
```python
class CommonElementsFinder:
    def __init__(self, array1, array2):
        """Initialize with two sorted arrays."""
        self.array1 = array1
        self.array2 = array2

    def find_common_elements(self):
        """Finds common elements between two sorted arrays without duplicates using two-pointer technique."""
        common_elements = []
        i, j = 0, 0  # Pointers for both arrays
        
        while i < len(self.array1) and j < len(self.array2):
            if self.array1[i] == self.array2[j]:  # If elements are equal, add to result
                if not common_elements or common_elements[-1] != self.array1[i]:  # Avoid duplicates
                    common_elements.append(self.array1[i])
                i += 1
                j += 1
            elif self.array1[i] < self.array2[j]:  # Move the smaller pointer forward
                i += 1
            else:
                j += 1
        
        return common_elements

arr1 = [1, 2, 2, 3, 4, 5, 6]
arr2 = [2, 2, 4, 6, 6, 7, 8]

finder = CommonElementsFinder(arr1, arr2)
result = finder.find_common_elements()
print("Common elements:", result)
```

---

### **Explanation**
1. **Encapsulation**: The `CommonElementsFinder` class encapsulates the logic.
2. **Constructor (`__init__`)**: Initializes the sorted arrays.
3. **Method `find_common_elements`**:
   - Uses **two-pointer technique** to efficiently find common elements.
   - Ensures no **duplicate elements** in the result.
4. **Efficiency**:
   - **Time Complexity**: \( O(n + m) \) → Linear, as each element is processed once.
   - **Space Complexity**: \( O(1) \) (ignoring output storage).

---

### **Output**
```txt
Common elements: [2, 4, 6]
```