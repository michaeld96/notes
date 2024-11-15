# `protected`

This keyword is an access modifier, and what `protected` does is it allows derived classes to have
access of this inherted value. In the example below, `Student` inherits the valud `Id` from
the base class.

```cs
class StudentBase
{
    protected int Id = 10;
};

class Student : StudentBase
{
    public int AccessId()
    {
        return Id;
    }
}

class Program
{
    static void Main()
    {
        Student Michael = new Student();
        Console.WriteLine(Michael.AccessId());
    }
}
```