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
__Implementing various algorithms like insertion sort, bubble sort and merge sort in Python. Implementing Dynamic Programming problems in Python.__



## Day 3 : PyTorch Basics
__Working with pyTorch basics including: tensors, autograd, basics of neural networks. Learning to train a classifier and data parallelism.__

**Tensors** constructing an unitialized matrix: gets initialized to numbers in memory `torch.empty()`. Constructing a randomly initialized matrix can be done using `torch.rand()` and `torch.randn` where `rand()` creates a uniform distribution between zero and one and `randn()` creates a gaussian distribution with mean 0 and standard deviation 1.

If we create a tensor based on an existing tensor `torch.zeros_like()` it copies all the properties like size and data type from the old tensor unless new values are provided by the user. The element-wise addition of two tensors with the same dimensions results in a new tensor with the same dimensions where each scalar value is the element-wise addition of the scalars in the parent tensors `(x+y)` and `torch.add(x,y,out=result)` both add two tensors while the second provides an option of storing the result in result tensor. If we use `add_` it performs in place addition. Any operation that mutates the current tensor is followed with an _ .
1. Tensor multiplication: `torch.mm(x,y,out=result)` here and y should have agreeing dimensions.
2. Tensor copy: `x.copy_(y)` copies the tensor y into tensor x in-place.
3. Tensor transpose: `x.t_()` this saves the transpose of x in-place.

**Broadcasting** talks about how smaller arrays broadcast across to the larger array subject to their dimensions untill they have compatible shapes. Two tensors are broadcastable if they follow the following rules:
1. Each tensor has atleast one dimension.
2. When iterating over dimension sizes, starting with trailing dimension, the dimension sizes must either be equal, one of them equal to one or one of them non-existent.

**Autograd** provides automatic differentiation for all operations on tensors. If we set the attribute `.requires_grad` as  `True` then it starts to track all operations on it. Once finished computation `.backward()` helps compute all gradients automatically computes gradients. We can prevent tracking history by wrapping the code block with `torch.no_grad()`. Each  tensor has a `.grad_fn` attribute that references the function that created the tensor. `.requires_grad_(...)` changes an existing tensor's `required_grad` flag in place. The default value of the flag is zero.
