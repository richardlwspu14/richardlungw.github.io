# Company of Employees: Fixed Sized Array List
## Goal: 
Your assignment is to write a C++ program to read a text file containing the information of the employees of a company, load them into memory and perform some basic human resources operations. This assignment will help you practice: multiple file programming, classes, public and private methods, dynamic memory allocation, constructors and destructors, arrays and files.
## Implementation
This lab assignment gives you the opportunity to practice creating classes and using dynamic memory in one of the required classes.
There are two classes to implement `Employee` and `Company`. As you can see in the description table, `Company` has an array of `Employees`. This list of employees is modeled using an array of `Employee*` (pointers to Employees). These employees are created dynamically when they are added to the list. Note that if the list is full, it will not be possible to add them.

### Program Menu

Your program should output the following menu:

```
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit
```
## Sample Output:
```
ML-ARIAS:employee-list-fixed-array-full arias$ make
g++ -c menu.cpp -std=c++11 -Wall
g++ -c company.cpp -std=c++11 -Wall
g++ -c employee.cpp -std=c++11 -Wall
g++ menu.o company.o employee.o -o company -std=c++11 -Wall
ML-ARIAS:employee-list-fixed-array-full arias$ ./company
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

1
Input filename: notfound.txt
Unable to open the file notfound.txt
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

1
Input filename: employees1.txt
9 Records read from file employees1.txt
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

3
ID:    1 Name: Peter      Salary:        250 Manager ID:    0
ID:    2 Name: Dio        Salary:        100 Manager ID:    0
ID:    3 Name: Silvia     Salary:        150 Manager ID:    1
ID:    4 Name: Leonel     Salary:       1801 Manager ID:    0
ID:    5 Name: Jon        Salary:       3500 Manager ID:    1
ID:    9 Name: Jon        Salary:       4100 Manager ID:    2
ID:   10 Name: Anna       Salary:       2250 Manager ID:    2
ID:   11 Name: Melissa    Salary:       1450 Manager ID:    1
ID:   16 Name: Nicole     Salary:         50 Manager ID:    0
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

4
Search for name: Jon
ID:    5 Name: Jon        Salary:       3500 Manager ID:    1
ID:    9 Name: Jon        Salary:       4100 Manager ID:    2
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

4
Search for name: Olga
Name not found on database
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

5
Search for ID: 5
ID:    5 Name: Jon        Salary:       3500 Manager ID:    1
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

5
Search for ID: 7
7 not found
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

6
Search for ID: 5
Employee with ID: 5 has manager:
	ID:    1 Name: Peter      Salary:        250 Manager ID:    0
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

99
Incorrect menu option!
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

incorrect
Incorrect input!
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

7
Input Employee Information
Employee id: 5
ID already exists!
Do you want to add use another ID yes
Input Employee Information
Employee id: 5
ID already exists!
Do you want to add use another ID no
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

7
Input Employee Information
Employee id: 7
Employee name: Grace
Employee salary: 1300
Employee's Boss ID: 2
Employee added successfully
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

3
ID:    1 Name: Peter      Salary:        250 Manager ID:    0
ID:    2 Name: Dio        Salary:        100 Manager ID:    0
ID:    3 Name: Silvia     Salary:        150 Manager ID:    1
ID:    4 Name: Leonel     Salary:       1801 Manager ID:    0
ID:    5 Name: Jon        Salary:       3500 Manager ID:    1
ID:    7 Name: Grace      Salary:       1300 Manager ID:    2
ID:    9 Name: Jon        Salary:       4100 Manager ID:    2
ID:   10 Name: Anna       Salary:       2250 Manager ID:    2
ID:   11 Name: Melissa    Salary:       1450 Manager ID:    1
ID:   16 Name: Nicole     Salary:         50 Manager ID:    0
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

7
Database is full
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

8
Database is Full
1. Load from File
2. Save to File
3. List all Employees
4. Search by Name
5. Search by ID
6. Find Employee Boss Information
7. Add new Employee
8. Check if Database is Full
9. Exit

9
```
