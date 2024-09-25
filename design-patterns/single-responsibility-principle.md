# Single Responsibility Principle (SRP)

This states that every class should be responsible for only a piece
of functionality; it should need to change only if that required 
functionality changes.

## Example:
Have a class named `TaxCalculator` that calculates the tax due on a 
paticular product, taking into account the user's location in the 
world. How this makes it a SRP is that this class only does one thing,
calculates the taxes based on product and location.