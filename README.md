# Learning Object-Oriented Programming in Python

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/JoseAlberto88/Learning-Object-Oriented-Programming-Python/blob/main/OOP_with_turtle_library_py.ipynb)

This repository holds one Jupyter notebook where I learn object-oriented programming (OOP) by writing small programs. I start with the `turtle` library to see objects in use. Then I write my own classes and work up to inheritance, multiple inheritance, and special methods.

Most exercises follow the same pattern: a written description of what the program should do, then the code, then the output.

## What the notebook covers

| Section | Concepts | Programs |
|---|---|---|
| 1. Turtle drawings | Objects, methods, and attributes of a class someone else wrote | Two lines, a filled star, 5 drawing challenges |
| 2. First classes | `class`, `__init__`, `self`, attributes, methods | App login, Online Course Management System, Travel Planner and Cost Calculator, Guest Management and Loyalty Program |
| 3. Inheritance | Parent and child classes, `super()`, method overriding | Animal clinic, Superhero and Flying Superhero, Library Management System, Country Information System |
| 4. Multiple inheritance | Classes with two or more parents, method resolution order | Hybrid car, Savings account, Customer Loyalty System, Online Shopping System |
| 5. Special methods | `__str__`, `__eq__`, `__add__`, `__sub__`, `__len__` | Staff Tracking System, Sports Match Comparison System, Library Item System |

That adds up to 5 turtle challenges and 15 class-based programs. Each section opens with short notes on the concept.

## Example

This is the child class from the superhero exercise in section 3. `Flying` inherits from `Superhero`, reuses its `__init__`, and replaces its `use_power()` method.

```python
class Flying(Superhero):
  def __init__(self, name, power, speed):
    super().__init__(name, power)
    self.speed = speed

  def use_power(self):
    print(f"{self.name} is flying at the speed of {self.speed} miles per hour")

superman = Flying("Clark Kent", "Flight", 250)
superman.intro_hero()   # inherited from Superhero
superman.use_power()    # overridden in Flying
```

```
I am Clark Kent and I have the power Flight
Clark Kent is flying at the speed of 250 miles per hour
```

## How to run it

### In Google Colab (recommended)

1. Click the "Open in Colab" badge at the top of this page.
2. Run the `!pip install ColabTurtlePlus -q` cell. The turtle drawings need it.
3. Run the cells from top to bottom.

### On your own computer

```bash
git clone https://github.com/JoseAlberto88/Learning-Object-Oriented-Programming-Python.git
cd Learning-Object-Oriented-Programming-Python
jupyter notebook OOP_with_turtle_library_py.ipynb
```

Sections 2 to 5 need only Python 3. The turtle cells in section 1 depend on ColabTurtlePlus, which is built for Google Colab, so run those there.

### Before you run

- Some programs ask you to type values: the Online Course system, the Travel Planner, the Guest Management program, and the Animal clinic. Run those cells one at a time.
- The Guest Management program expects each guest on one line, separated by slashes: `john/doe/8/45`.
- The Online Shopping program writes two files to the working folder: `customer_cart.txt` and `seller_products.txt`.

## What I learned

- Two objects from the same class keep separate data. Changing the color of one turtle never changes the other.
- Inside a loop over a list of objects, use the loop variable, not `self`. My first Guest Management version used `self` and printed the first guest three times. I kept the broken version in the notebook next to the fix.
- `super().__init__()` lets a child class reuse the parent's setup code, so I only write the new attributes.
- With multiple inheritance, Python checks the parents from left to right. If two parents have a method with the same name, only the first one runs. The hybrid car exercise avoids this with two names, `get_range()` and `get_fuel_range()`.
- Special methods connect my classes to Python's own syntax. `print(obj)` calls `__str__`, `==` calls `__eq__`, `+` calls `__add__`, and `len(obj)` calls `__len__`.

