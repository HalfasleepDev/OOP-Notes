# Object Oriented Programing Notes 1

I think OOP is kewl!

```python
# Example class

class person:
    def __init__(self, name):
        seld.name = name
        
    def __str__(self):
        return f"Person Object called: {self.name}"
        
    def __repr__(self):
        return self.__str__()
        
```

## Definitions
- Object Oriented Programming
- Encapsulation
- Inheritance
- Polymorphism
- Override

## 1. Object Oriented Programming

- A Programming paradigm that focuses custom classes for special objects to solve problems
- **Class:** A description of a new object that contain attributes and methods.
    - Example:
    ```python
    class ClassName: # Class names are capitalized
	    pass # This is an empty block
    #end 
    ```
- **Attributes:** Data and Variables that belong to the class.
    - Example:
    ```python
    class ClassName:
        def __init__(self, attribute): # Initialization of the class and attribute
            self.att = attribute
    ```
- **Methods:** Functions within the class.
    - Example:
    ```python
    class ClassName:
        def __init__(self, attribute): 
            self.att = attribute
            
        def method1(self)
            print('This is the attribute of this class', self.att)
    ```
- **Object:** An instance of any class with in a program.
 
## 2. Encapsulation
- Encapsulation hides/resstricts classes objects' certain attributes and methods. This is done for data protection and restricting certain methods to be callable.
- This is done with a double underscore `__`.
    - Example:
    ```python
    class Student:
      def __init__(self,nameF, nameL, num):
        self.__firstName = nameF
        self.__lastName = nameL
        self.__studentNumber = num
  
      def setFirstName(self, newName):
        self.__firstName = newName

      def getFirstName(self):
        return self.__firstName
    ```
    Doing this is common practice.
    
## 3. Inheritance
- **Single inheritance:** A subclass inheriting the features of a single parent class
    - Example:
    ```python
    class ParentClassName:
        “”” Define Parent Class “””
	
	
	

    class InheritanceClass(ParentClassName):
        “”” Define Inherited Class “””

        def __init__(self, param, param2):
            ParentClassName.__init__(self, param)
            self.param2 = param2
    ```
- **Multiple inheritance:** A subclass inheriting the features of a multiple parent classes
    - Example:
    ```python
    class SuperClass1:
    # features of SuperClass1

    class SuperClass2:
        # features of SuperClass2

    class MultiDerived(SuperClass1, SuperClass2):
        # features of SuperClass1 + SuperClass2 + MultiDerived class
    ```
- **Multilevel inheritance:** A subclass is inheriting from another subclass
    - Example:
    ```python
    class SuperClass:
    # Super class code here

    class DerivedClass1(SuperClass):
        # Derived class 1 code here

    class DerivedClass2(DerivedClass1):
        # Derived class 2 code here
    ```
## 4. Polymorphism
- A method that can be used across different classes and object that is dependent on the parameters.
    - Example:
    ```python
    class Parent:
	def method(self):
		pass

    class Child(Parent):
        def method(self):
            # something different
            # Polymorphed to something else…
            # Same method name!
            pass
    ```
    
## 5. Override
- **Overloading:** Two methods in one class that have the same method name, but different parameters. **However there is no overloading in python 3**.
    - Illegal example:
    ```python
    class Person:
        def __init__(self, name, age):
            self.__name = name
            self.__age = age

        def show(self):
            return self.__name

        def show(self, num):
            return "%s %d" % (self.__name, self.__age)
    ```
- **Overriding:** Two methods with the same method name and parameters. For example, overriding allows the child class to provide specific implementation for a method that exists in the parent class
    - Example:
    ```python
    class Bear:
        def sound(self):
            print("Groarrr")

    class Dog:
        def sound(self):
            print("Woof woof!")

        def makeSound(animalType):
            animalType.sound()
    
    bearObj = Bear()
    dogObj = Dog()

    makeSound(bearObj)
    makeSound(dogObj)
    ```
