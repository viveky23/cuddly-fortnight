# 100-days of Machine Learning and Deep Learning in Python
## Day 1 : Python Practice
__Read about and implemented Python classes, functions and reading csv files. Also implemented various sorting algorithms Python to practice coding in Python.__

**Python classes** can be constructed using def \_\_init\_\_(self [, Arguments]) where we can also have default values for all these arguments so that if the user fails to provide these values they default to the given values. We can also declare class accessors in the class definition i.e. GerName(), GetAge() etc. which can be used to access the underlying class variables however do not allow write access to them. 

    def GetName(self):
        return self.Name

Similarly we can use setters to set variable names which provide write-only access to the underlying value. 

    def SetName(self, name)
        self.name = name

We also need to declare \_\_str\_\_() method if we want the user to be able to print the object in a particular format.

***
**Reading a csv file** is done using the reader object which will iterate over lines in the given csv files. Similarly csv.writer object is used to convert the user's data into delimited strings on a given file like object. csv.DictReader operates like a regular reader however maps the information in each row to an OrderedDict whose keys are given by an optional fieldnames parameter.
   
    with open('example.csv') as csvfile:
        readCSV = csv.reader(csvfile, delimiter=',')

    with open('names.csv', newline='') as csvfile:
       reader = csv.DictReader(csvfile)
       for row in reader:
           print(row['first_name'], row['last_name'])
           

## Day 2 : Python Practice
Implementing various algorithms like insertion sort, bubble sort and merge sort in Python. Implementing Dynamic Programming problems in Python.
