# PRG101-lab10
### Submission Details

In this lab, you will work on a complete example of classes implementing inheritance. Write the scripts in Github Codespaces. Take screenshots at all logical steps and name your screenshots as instructed.
### Lab Objectives
- To understand the concepts of inheritance, superclass, subclass, polymorphism.
- To implement inheritance in Python and explore how a child class can use and extend the functionality of a parent class.
- To understand how constructors `__init__()` methods work in Python and explore their role in inheritance.

## INVESTIGATION 1: INHERITANCE

Inheritance is a fundamental concept in object-oriented programming (OOP) that allows a class to inherit attributes and methods from another class. This promotes code reuse, extending functionality and can make complex systems easier to manage.
A superclass (also known as a parent class or base class) is a class that is inherited by another class. A subclass (also known as a child class or derived class) is a class that inherits from a superclass. Constructors `__init__()`  methods are special methods in Python used to initialize objects when they are created. In inheritance, the child class can call the parent's constructor to initialize attributes from the parent class.

In this example, Animal is the superclass, and Dog is the subclass. In a subclass, you can call the constructor of the superclass to initialize the inherited attributes. This is done using the super() function. The Dog class inherits the name attribute and speak method from Animal but overrides the speak method to provide a specific implementation.


```Python
# Superclass
class Animal:
    def __init__(self, name):
        self._name = name
    def speak(self):
        return f"{self._name} makes a sound."

# Subclass
class Dog(Animal): # To inherit from a parent class, a child class must pass the name of parent class
# as a function argument in class definition.
    def __init__(self, name, breed):
        # Call the superclass constructor
        super().__init__(name)
        self._breed = breed
def speak(self):
        return f"{self._name} barks."
    
    def display_info(self):
        return f"{self._name} is a {self._breed}."

# Creating an object of the subclass
dog = Dog("Buddy", "Golden Retriever")
print(dog.display_info())  # Output: Buddy is a Golden Retriever.
```

## lab10a: Implementing a Simple Inheritance Structure with Person and Student
### Create the `Person` class
- Create a new .py file called `person.py`.
- Create a class called `Person` (Parent Class) in the `person.py` with the following:
    - Attributes: `name: str`, `age: int`
    - Method: `display_info()` to print the name and age of the person.
- You should start  by writing the constructor `__init__` that initializes the name and age attributes.
    - Example: `def __init__(self, name, age)`
- After the constructor, create the `display_info()` method. This method should print name and age of the person.

### Create the `Student` class
- Create another .py file called `student.py`
- Create a class called `Student` (Child Class) in the `student.py` that inherits from `Person` and has an additional attribute `student_id: str`.
- You should start by writing the constructor` __init__` that initializes the name, age, and student_id attributes.
    - Use `super().__init__(name, age)` in the `Student` constructor to call the `Person` constructor.
    - Next you should create the instance variable `student_id`.
- Method: Create a method called `display_student_info()` to print the `name`, `age`, and `student_id` in the `Student` class.
### Test your classes
- Create a third file called `person_student_tester.py`.
- Write the main function in the tester file.
- Create an instance of the `Person` class with the name "Alice" and age 40. Call `display_info()` for this instance.
- Create an instance of the `Student` class with the name "Bob", age 20, and student ID "S12345". Call `display_student_info()` for this instance.
- Take a screenshot of main() from `person_student_tester.py` also capturing the output at this point. Name the screenshot as lab10a_output1.png. Add this screenshot in the pdf.
- Next call the `display_info()` method for the `Student` object.
- What do you oberve? `display_info()` is not the `Student` class method. Explain the output in your own words  as comments in the tester file.
- At this point again take a screenshot of main() from `person_student_tester.py` also capturing the output. Name the screenshot as lab10a_output2.png. Add this screenshot in the pdf.
- Modify the Student class to use the `super()` function to call the `display_info()` method of the parent class inside its `display_student_info()` method. Why is using `super()` useful when extending functionality in the child class?
- Take screenshot of all files showing the code and your explanation as well as the output. Name your screenshots as:
    - lab10a_Person.png
    - lab10a_Student.png
    - lab10a_tester_output.png
- Add the screenshots in the pdf.

## INVESTIGATION 2: METHOD OVERRIDING

Method Overriding in Python allows a subclass to provide a specific implementation of a method that is already defined in its superclass. When a method in a subclass has the same name, parameters, and return type as a method in its superclass, the method in the subclass overrides the one in the superclass.

### lab10b Adding methods in sub classes to override method in superclass 
- In the Student class add the `display_info()` method to override it from the parent class. In this method print `student ID`.
- What happens now when you call `display_info()` on the Student instance?
- Explain this in comments, take screenshots of `display_info()` along with comments. Name the screenshot as lab10b_displayinfo.png
- Also take a screenshot of the output and add them in the pdf. Name the screenshot as lab10b_tester_output.png

### lab10c Adding methods in sub classes to override method in superclass 
- Modify `display_info()` of `Student` class such that it first prints `name` and `age` attributes of Person class and then `student ID`. (hint: you should achieve this by using `super().display_info()` of `Person` class to print name and age and then print `student ID`)
- You can now delete the method `display_student_info()` from 'Student` class. We do not need this method. You should understand by now that how we extended the functionality of `Student` class by overriding the `display_info()` function.
- Take screenshot of `display_info` from `Student` class. Name the screenshot as lab10c_displayinfo.png
- Also take a screenshot of the output and add them in the pdf. Name the screenshot as lab10c_tester_output.png

## INVESTIGATION 3: POLYMORPHISM
Polymorphism is a very useful concept in OOP that results into compact code without duplications. Polymorphism is the ability for a programming language to present a single interface for different data types and objects to respond uniquely to the same message. Polymorphism involves minimum three components, a base class, a derived class and a polymorphic function that expects base class object as a parameter. You can pass base classs or derived class object to this function, calling any class method in this function will call the appropriate method of the passed object.

### lab10d Testing Polymorphism
- Create a function `print_details(person)` in `person_student_tester.py` that takes an object and calls display_info(). Test this function with both a Person instance and a Student instance?
- What is printed when you call this function by passing a `Person` object and when you pass `Student` object?
- In the context of these two classes, in your own words, explain what is polymorphic behavior in the above example?
-  Take screenshot of `print_details(person)` and the output and add in the pdf. Name the screenshot as lab10d.png

## Lab 10 Sign-Off
- Submit the screenshots of each individual script, the screenshot must show your scripts and command line interface and output.
- The screenshot must also show your username on github codespaces.
- Submit individual screenshots of the following scripts on blackboard. If the screenshots do not correctly show the information mentioned above, you will get zero marks for the lab.
    - lab10a_output1.png
    - lab10a_output2.png
    - lab10a_Person.png
    - lab10a_Student.png
    - lab10a_tester_output.png
    - lab10b_displayinfo.png
    - lab10b_tester_output.png
    - lab10c_displayinfo.png
    - lab10c_tester_output.png
    - lab10d.png
