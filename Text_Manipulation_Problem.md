## **Text Manipulation Problem**
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
```bash
grep "IT" employees.txt | awk -F',' '{print $1","$2","$3}' | sed 's/IT/Tech Team/' | awk -F',' '{print $1","toupper($2)","$3}'
```

#### **Explanation:**
1. `grep "IT" employees.txt` → Filters only lines where the department is "IT".
2. `awk -F',' '{print $1","$2","$3}'` → Extracts "ID", "Name", and "Department" columns.
3. `sed 's/IT/Tech Team/'` → Replaces "IT" with "Tech Team".
4. `awk -F',' '{print $1","toupper($2)","$3}'` → Converts names to uppercase.

##### **Output:**
```txt
101,AKASH BANERJEE,Tech Team
103,EMILY DAVIS,Tech Team
105,CHRIS HEMSWORTH,Tech Team
```

---

