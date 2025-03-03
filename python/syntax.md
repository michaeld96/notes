# Syntax

## Packing with `*agrs`
The single `*` here means all the arguments, put them in a list.

```py
def fun(name, *args):
    print(name)
    print(args) # this will print all the arguments.

fun("mike", 2, 4, 7, "here is a string", 'c')
```

This prints
```
mike
(2, 4, 7, 'here is a string', 'c')
```

## Packing with `*kwargs`
This double `*` packs all the arguments into a dictionary. 

```py
def fun(greetings, **kwargs):
    print(greetings)
    print(kwargs)

fun("howdy!", name="michael", role="swe", num=1234)
```

This prints 

```
howdy!
{'name': 'michael', 'role': 'swe', 'num': 1234}
```

## Unpacking Arguments
We can unpack arguments for a list with single `*` or a dictionary `**`.
Below are two examples:

### With a List
```py
def printAddThreeArgs(x, y, z):
    print(x + y + z)

nums = [6, 13, 5]
printAddThreeArgs(*nums) # Prints: 24
```

### With a Dictionary
```py
def printUser(name, age, active):
    print(name, age, active)

User = {
    "name" : "Michael",
    "age" : 42,
    "active" : True
}
printUser(**User) # Prints: Michael, 42, True
```

