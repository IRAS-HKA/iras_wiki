[Back to Home](../../README.md) / [1.5 Software Guidelines](1.5-software_guidelines.md) / **How to Document Code**

<hr>

## General

### Philosophy
When writing program code, you should ask yourself two questions regarding commenting: 

> What will my future self, or a work colleague need when doing development or maintenance work on this part of the software?

and:

> What would I wish I had found here?

In addition you should keep in mind that the written code tells you *how*, but the comments tell you *why*.

## Python
### One liners 
You should, at various points in your code, add simple remarks of whats happening as shown in the following example. Even if the meaning of the code is quite clear, skimming the comments saves the reader significant time.

```python
""" Array of all x coordinates with padding """
self._x_coords = np.arange(
	x_range[0] - resolution,
	x_range[1] + 2 * resolution,
	resolution
)

""" Array of all y coordinates with padding """
self._y_coords = np.arange(
	y_range[0] - resolution,
	y_range[1] + 2 * resolution,
	resolution
)

""" Calculate own size """
self._height = len(self._y_coords)
self._width = len(self._x_coords)

```

### Comment Anchors
The following four keywords should be used to identify these special situations for future reference. 

* **TODO**: Write a simple one-liner of the specific task at this position
* <mark>**REVIEW**: This code requires additional review</mark>
* **FIXME**: At this point in the code a known bug is located which needs fixing. Please describe the cause and result if possible.
* <mark>**STUB**: This is some placeholder code</mark>

### Commenting Objects
The NumPy/SciPy Docstring format should be used while commenting python code. Each object needs a short, one line, description and an optional, longer explanation. In addition, depending on the object type a list of properties is specified. All necessary information is listed in the table below and can be seen in the appended example.

|       | Class                         | Function          | \_\_init\_\_() |
| :---: | ----------------------------- | ----------------- | -------------- |
|   1   | Short description             | Short description | No description |
|   2   | Long description              | Long description  | Parameters     |
|   3   | Attributes (including @param) | Parameters        |                |
|   4   | Methods                       | Returns           |                |

#### Example
```python
class Employee:
    """
    A class representing a single employee

    A longer explanation can be added in this area, for example describing instructions for a user. 
	
    Attributes
    ----------
    affiliation : int
	the time in full years the employee is with the company
    age : int
	a number representing the age of the employee
    name: str
	a string consisting of the pre- and surname of the employee		
        both names are separated with a underscore '_'
    salary: float
	the exact salary of the employee in euros
		
	
    Methods
    -------
    checkPayRaise(interval=3)
	Returns new salary depending on affiliation duration
	
    incAffiliation()
	Increases the company affiliation duration by 1 (one) year
    """
	
    _affiliation: 	int
    _age: 		int
    _prename:		str
    _salary:		float
    _surname:		str
	
    @property 
    def affiliation(self) -> int:
	return self._affiliation
		
    @property 
    def age(self) -> int:
	return self._age
		
    @age.setter
    def age(self, age: int) -> None:
	self._age = age
	
    @property 
    def name(self) -> str:
	return self._prename + "_" + self._surname
	
    @property 
    def salary(self) -> float:
	return self._salary
	
    def __init__(self, prename: str, surname: str, affiliation: int = 0):	
        """	
	Parameters
	----------
	prename : str
	    The prename of the employee
	surname : str
           The surname of the employee
	affiliation : int, optional
	    Company affiliation in full years (default = 0)
	"""
		
	self._prename = prename
	self._surname = surname
        self._affiliation = affiliation
	
    def checkPayRaise(self, interval: int = 3) -> float:
	"""
	Checks if a pay raise is due depending on years of company affiliation
	
	Parameters
	----------
	interval : int, optional
	    Interval in years in which a pay raise is due (default = 3)
			
	Returns
	-------
	float
	    New salary
	"""
		
	# some code
		
    def incAffiliation(self) -> int:
	"""
	Increases the company affiliation duration by 1 (one) year
		
	Returns
	-------
	int
	    New company affiliation duration
	"""
		
	# some code
```

## C#

### One liners 
You should, at various points in your code, add simple remarks of whats happening as shown in the following example. Even if the meaning of the code is quite clear, skimming the comments saves the reader significant time.

```csharp
/// Print pythagorean theorem for reference
Console.WriteLine("a^2 + b^2 = c^2");  
```

### Commenting Objects

Analogous to the guidelines for documenting Python code, the same basic informations is expected for C#. The position of the documentation however, is in front of the object to be documented. All necessary information is listed in the table below and can be seen in the appended example.

|       | Class       | Function    | Constructor |
| :---: | ----------- | ----------- | ----------- |
|   1   | Description | Description | Parameters  |
|   2   | Attributes  | Parameters  |             |
|   3   |             | Returns     |             |


#### Example

```csharp
/// <summary>  
/// A class representing a single employee
/// A longer explanation can be added in this area, for example describing instructions for a user.
/// </summary>
public class Employee:

    /// <summary> 
    /// the time in full years the employee is with the company
    /// </summary>
    public int affiliation => 0;

    /// <summary> 
    /// a number representing the age of the employee
    /// </summary>
    public int age;

    /// <summary> 
    /// a string consisting of the pre- and surname of the employee
    /// both names are separated with a underscore '_'
    /// </summary>
    public string name;

    /// <summary> 
    /// the exact salary of the employee in euros
    /// </summary>
    public float salary;

    /// <param name="prename"> The prename of the employee </param> 
    /// <param name="surname"> The surname of the employee </param> 
    /// <param name="affiliation"> Company affiliation in full years (default = 0) </param>
    public Employee(string prename, string surname, int affiliation_duration = 0)
    {
        name = prename + surname
        affiliation = affiliation_duration 
    }

    /// <summary>
    /// Checks if a pay raise is due depending on years of company affiliation
    /// </summary>
    /// <param name="interval"> Interval in years in which a pay raise is due (default = 3) </param>
    /// <returns> New salary </returns>
    public float checkPayRaise(int interval = 3)
    {
        /// some code
    }

    /// <summary>
    /// Increases the company affiliation duration by 1 (one) year
    /// </summary>
    /// <returns> New company affiliation duration </returns>
    public int incAffiliation()
    {
        /// some code
    }

```
