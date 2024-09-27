# Singleton

This is an object that is only instantiated once and is accessible
throughout the program.

```cpp
class Singleton
{
private:
    Singleton(); // make ctor private.
    Singleton(const Singleton&) = delete; // delete copy ctor.
    Singleton& operator=(const Singleton&) = delete; // delete assignment.
};
```