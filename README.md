# PYTHON_OOPS

Destructors:
======================
* Destructor is a special method and the name should be __del__
* Just before destroying an object Garbage Collector always calls destructor to perform clean up
  activities (Resource deallocation activities like close database connection etc).
* Once destructor execution completed then Garbage Collector automatically destroys that object.
Note: The job of destructor is not to destroy object and it is just to perform clean up activities.

Note:
If the object does not contain any reference variable then only it is eligible fo GC. ie if the
reference count is zero then only object eligible for GC


Polymorphism
===========================
Poly means many. Morphs means forms.
Polymorphism means 'Many Forms'.

Eg1: Yourself is best example of polymorphism.In front of Your parents You will have one type of
behaviour and with friends another type of behaviour.Same person but different behaviours at
different places,which is nothing but polymorphism.

Eg2: + operator acts as concatenation and arithmetic addition

Eg3: * operator acts as multiplication and repetition operator

Eg4: The Same method with different implementations in Parent class and child
     classes.(overriding)

Related to polymorphism the following 4 topics are important

1. Overloading
	1. Operator Overloading
	2. Method Overloading
	3. Constructor Overloading
2. Overriding
	1. Method overriding
	2. constructor overriding


Overloading:
===================================
* We can use same operator or methods for different purposes.
Eg1: + operator can be used for Arithmetic addition and String concatenation

	print(10+20)#30
	print('Raj'+'Prudhvi')#RajPrudhvi

Eg2: * operator can be used for multiplication and string repetition purposes.

	print(10*20)#200
	print('raj*3)#rajrajraj

Eg3: We can use deposit() method to deposit cash or cheque or dd

	deposit(cash)
	deposit(cheque)
	deposit(dd)

There are 3 types of overloading

1. Operator Overloading
2. Method Overloading
3. Constructor Overloading

1. Operator Overloading:
----------------------------------
We can use the same operator for multiple purposes, which is nothing but operator overloading.
Python supports operator overloading.

Eg1: + operator can be used for Arithmetic addition and String concatenation

	print(10+20)#30
	print('Raj'+'Prudhvi')#RajPrudhvi

Eg2: * operator can be used for multiplication and string repetition purposes.

	print(10*20)#200
	print('raj'*3)#rajrajraj

2. Method Overloading:
----------------------------------
If 2 methods having same name but different type of arguments then those methods are said to be 
overloaded methods.

	Eg: m1(int a)
	    m1(double d)

* But in Python Method overloading is not possible.
* If we are trying to declare multiple methods with same name and different number of arguments
  then Python will always consider only last method.


 How we can handle overloaded method requirements in Python:
Most of the times, if method with variable number of arguments required then we can handle
with default arguments or with variable number of argument methods.
Demo Program with Default Arguments:
class Test:
   def sum(self,a=None,b=None,c=None):
   if a!=None and b!= None and c!= None:
      print('The Sum of 3 Numbers:',a+b+c)
   elif a!=None and b!= None:
      print('The Sum of 2 Numbers:',a+b)
   else:
      print('Please provide 2 or 3 arguments')
   t=Test()
   t.sum(10,20)
   t.sum(10,20,30)
   t.sum(10)


3. Constructor Overloading:
----------------------------------------
* Constructor overloading is not possible in Python.
* If we define multiple constructors then the last constructor will be considered.


Method overriding:
----------------------
What ever members available in the parent class are bydefault available to the child class through
inheritance. If the child class not satisfied with parent class implementation then child class is
allowed to redefine that method in the child class based on its requirement. This concept is called
overriding.

Overriding concept applicable for both methods and constructors.


Exception Handling
-----------------------------
In any programming language there are 2 types of errors are possible.

1. Syntax Errors
2. Runtime Errors

1. Syntax Errors:
------------------------------
The errors which occurs because of invalid syntax are called syntax errors.

Eg 1:
------------------------
x=10
if x==10
   print("Hello")

SyntaxError: invalid syntax

Eg 2:
------------------------
print "Hello"

SyntaxError: Missing parentheses in call to 'print'

Note:
----------------
Programmer is responsible to correct these syntax errors. Once all syntax errors are corrected then
only program execution will be started.

2. Runtime Errors:
==============================
* Also known as exceptions.
* While executing the program if something goes wrong because of end user input or programming logic
  or memory problems etc then we will get Runtime Errors.

Eg: print(10/0) ==>ZeroDivisionError: division by zero
    print(10/"ten") ==>TypeError: unsupported operand type(s) for /: 'int' and 'str'


Note: Exception Handling concept applicable for Runtime Errors but not for syntax errors

What is Exception:
An unwanted and unexpected event that disturbs normal flow of program is called
exception.

	Eg:
	ZeroDivisionError
	TypeError
	ValueError
	FileNotFoundError
	EOFError




* It is highly recommended to handle exceptions. The main objective of exception handling
  is Graceful Termination of the program(i.e we should not block our resources and we
  should not miss anything)
* Exception handling does not mean repairing exception. We have to define alternative way
  to continue rest of the program normally.

Default Exception Handing in Python:
-----------------------------------------------
* Every exception in Python is an object. For every exception type the corresponding classes
  are available.
* Whevever an exception occurs PVM will create the corresponding exception object and
  will check for handling code. If handling code is not available then Python interpreter
  terminates the program abnormally and prints corresponding exception information to
  the console.The rest of the program won't be executed.

	Eg:
	print("Hello")
	print(10/0)
	print("Hi")

* Every Exception in Python is a class.
* All exception classes are child classes of BaseException.i.e every exception class extends
  BaseException either directly or indirectly. Hence BaseException acts as root for Python
  Exception Hierarchy.
* Most of the times being a programmer we have to concentrate Exception and its child
  classes.

Customized Exception Handling by using try-except:
----------------------------------------------------------
* It is highly recommended to handle exceptions.
* The code which may raise exception is called risky code and we have to take risky code
  inside try block. The corresponding handling code we have to take inside except block.


..............................................

try:
  Risky Code
except XXX:
  Handling code/Alternative Code

..............................................


Conclusions:
----------------------
1. within the try block if anywhere exception raised then rest of the try block wont be
executed eventhough we handled that exception. Hence we have to take only risky code
inside try block and length of the try block should be as less as possible.

2. In addition to try block,there may be a chance of raising exceptions inside except and
finally blocks also.

3. If any statement which is not part of try block raises an exception then it is always
abnormal termination.



try with multiple except blocks:
------------------------------------------
The way of handling exception is varied from exception to exception.Hence for every
exception type a seperate except block we have to provide. i.e try with multiple except
blocks is possible and recommended to use.


=>If try with multiple except blocks available then based on raised exception the
corresponding except block will be executed.

=>If try with multiple except blocks available then the order of these except blocks is
  important .Python interpreter will always consider from top to bottom until matched
  except block identified.


Default except block:
------------------------------
* We can use default except block to handle any type of exceptions.
* In default except block generally we can print normal error messages.

	Syntax:
	==================
	except:
	  statements


***Note: If try with multiple except blocks available then default except block should be
         last,otherwise we will get SyntaxError

Note:
---------------------
The following are various possible combinations of except blocks
	1. except ZeroDivisionError:
	1. except ZeroDivisionError as msg:
	3. except (ZeroDivisionError,ValueError) :
	4. except (ZeroDivisionError,ValueError) as msg:
	5. except :

finally block:
--------------------------
1. It is not recommended to maintain clean up code(Resource Deallocating Code or
Resource Releasing code) inside try block because there is no guarentee for the execution
of every statement inside try block always.

2. It is not recommended to maintain clean up code inside except block, because if there
is no exception then except block won't be executed.

* Hence we required some place to maintain clean up code which should be executed
  always irrespective of whether exception raised or not raised and whether exception
  handled or not handled. Such type of best place is nothing but finally block.

* Hence the main purpose of finally block is to maintain clean up code.


	try:
	  Risky Code
	except:
	  Handling Code
	finally:
	  Cleanup Code

The speciality of finally block is it will be executed always whether exception raised or not
raised and whether exception handled or not handled.


Types of Exceptions:
---------------------------------------
In Python there are 2 types of exceptions are possible.
1. Predefined Exceptions
2. User Definded Exceptions


1. Predefined Exceptions:
----------------------------------------
Also known as in-built exceptions
The exceptions which are raised automatically by Python virtual machine whenver a
particular event occurs, are called pre defined exceptions.

Eg 1: Whenever we are trying to perform Division by zero, automatically Python will raise
      ZeroDivisionError.

		print(10/0)

Eg 2: Whenever we are trying to convert input value to int type and if input value is not
int value then Python will raise ValueError automatically

		x=int("ten")===>ValueError

2. User Defined Exceptions:
------------------------------------------
* Also known as Customized Exceptions or Programatic Exceptions
* Some time we have to define and raise exceptions explicitly to indicate that something
  goes wrong ,such type of exceptions are called User Defined Exceptions or Customized
  Exceptions
* Programmer is responsible to define these exceptions and Python not having any idea
  about these. Hence we have to raise explicitly based on our requirement by using "raise"
  keyword.

Note:
raise keyword is best suitable for customized exceptions but not for pre defined
exceptions

How to Define and Raise Customized Exceptions:
------------------------------------------------------
Every exception in Python is a class that extends Exception class either directly or
indirectly.

Syntax:
	class classname(predefined exception class name):
		def __init__(self,arg):
			self.msg=arg

