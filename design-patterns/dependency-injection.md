# Dependency Injection

## Problem 

Let's say we have three classes `OrderTotalCalculator`, 
`ShippingCostService`, and `TaxCalculator`. Say `OrderTotalCalculator` 
needs access to an instance of `ShippingCostService` and 
`TaxCalculator`. Instead of creating an instance of a service whenever 
we need it, we can declare the dependencies and let another class
fill those dependencies for us, this is what is called *dependency injection* or called *Inverse of Control* (IOC).

