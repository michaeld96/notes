# Factory (OOP)

A factory is an object that creates other objects.

```cpp
class Person
{
public:
    int age;
    std::string name;
    Person(int in_age, std::string in_name) : age(in_age), name(in_name) { }
};

class PersonFactory // Typically a static class.
{
public: 
    static Person CreateDefaultPerson()
    {
        return Person(0, "");
    }
    static Person CreatePerson(int in_age, std::string in_name)
    {
        return Person(in_age, in_name);
    }
};

int main()
{
    Person defaultPerson = PersonFactory::CreateDefaultPerson();
    std::cout << defaultPerson.age << " " << defaultPerson.name << std::endl;
    
    Person customPerson = PersonFactory::CreatePerson(20, "Michael");
    std::cout << customPerson.age << " "<< customPerson.name << std::endl;
    
    return 0;
}
```