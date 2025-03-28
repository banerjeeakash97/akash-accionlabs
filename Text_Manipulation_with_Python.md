## **Text Manipulation Problem with Python**
File `employees.txt` containing employee details in the following format:

```txt
ID,Name,Department,Salary
101,Akash Banerjee,IT,75000
102,Will Smith,HR,62000
103,Emily Davis,IT,82000
104,Michael Brown,Finance,78000
105,Chris Hemsworth,IT,72000
```

#### **Task:**
1. Extract only employees from the "IT" department.
2. Replace all occurrences of "IT" with "Tech Team".
3. Convert all names to uppercase.
4. Display only the "ID", "Name", and "Updated Department" fields.

---

### **Solution**
```python
class Employee:
    def __init__(self, file_path):
        self.file_path = file_path
        self.employees = []

    def load_data(self):
        """Reads the employee file and loads data into a list"""
        with open(self.file_path, 'r') as file:
            lines = file.readlines()[1:]
            for line in lines:
                emp_id, name, department, salary = line.strip().split(',')
                self.employees.append({
                    "ID": emp_id,
                    "Name": name,
                    "Department": department,
                    "Salary": salary
                })

    def filter_IT(self):
        """Filters only employees from the 'IT' department"""
        self.employees = [emp for emp in self.employees if emp["Department"] == "IT"]

    def update_department(self):
        """Replaces 'IT' with 'Tech Team'"""
        for emp in self.employees:
            emp["Department"] = "Tech Team"

    def convert_names_to_uppercase(self):
        """Converts employee names to uppercase"""
        for emp in self.employees:
            emp["Name"] = emp["Name"].upper()

    def display_results(self):
        """Displays the final formatted output"""
        for emp in self.employees:
            print(f"{emp['ID']},{emp['Name']},{emp['Department']}")


processor = Employee("employees.txt")
processor.load_data()
processor.filter_IT()
processor.update_department()
processor.convert_names_to_uppercase()
processor.display_results()
```

---

### **Explanation**
1. **Encapsulation:** Wrapped logic inside an `Employee` class.
2. **Methods for Specific Tasks:** 
   - `load_data()` → Reads the file and parses data.
   - `filter_IT()` → Filters only "IT" employees.
   - `update_department()` → Renames "IT" to "Tech Team".
   - `convert_names_to_uppercase()` → Changes names to uppercase.
   - `display_results()` → Prints the final result.
3. **Efficiency:** The use of list comprehensions and in-place modifications makes it memory efficient.

##### **Output**
```txt
101,AKASH BANERJEE,Tech Team
103,EMILY DAVIS,Tech Team
105,CHRIS HEMSWORTH,Tech Team
```
