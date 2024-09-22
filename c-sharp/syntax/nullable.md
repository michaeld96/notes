# Syntax: 
## `?` - Nullable

Typically, this could be used for data fields for a record.

```cs
public class 
{
    [Key]
    public int Id { get; set; }
    public string? Name { get; set; }
}
```

The example above, we see that the `string?` field can be null.
