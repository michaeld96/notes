# YML or YAML

## Creating a Variable
```yml
name: Michael   # Strings can be in "", '', or none.
age: 24         # Int.
height: 6.7     # Float.
```

## Creating a List
This `people` list is key value pair.
```yml
people:
    - name: Michael
    - name: Kevin
    - name: Nick
```

Also, we care create lists like so:
```yml
eecs_classes = ['EECS183', 'EECS280', 'EECS281']
```
## Creating a Dictionary
```yml
michael: {name: Michael, age: 25, height: 6,7}
```

## Creating an Object
```yml
michael:
    name: Michael
    age: 25
    height: 6.7
```

## Creating a List of Objects
```yml
- michael:
        name: Michael
        age: 25
        height: 6.7
- kevin:
        name: Kevin
        age: 35
        height: 5.2
- nick:
        name: Nick
        age: 38
        height 6.5
```