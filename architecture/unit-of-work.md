# Unit of Work 

Unit of work creates an abstraction layer between the database and 
the business logic of an application.

## Example

Let's say we have two *entities* `Post` and `Comment`, and
these two entities have their own *repositories*, but we want to
make sure that both are saved on a single interaction to the 
database. Below is how we will implement Unit of Work:

1. Define the repository.

```cs
public interface IPostRepository
{
    void Add(Post post);
    Post GetById(int id);
}

public interface ICommentRepository
{
    void Add(Comment comment);
    Comment GetById(int id);
}
```
2. Implement the Unit of Work interface.

```cs
public interface IUnitOfWork : IDisposable
{
    IPostRepository Posts { get; }
    ICommentRepository Comments { get; }
    void Save();
}
```
3. Implement Unit of Work class.
```cs
public class UnitOfWork : IUnitOfWork
{
    private readonly BloggingContext _context;

    public IPostRepository Posts { get; private set; }
    public ICommentRepository Comments { get; private set; }

    public UnitOfWork(BloggingContext context, IPostRepository postRepository, ICommentRepository commentRepository)
    {
        _context = context;
        Posts = postRepository;
        Comments = commentRepository;
    }

    public void Save()
    {
        _context.SaveChanges(); // Commit all changes in one transaction
    }

    public void Dispose()
    {
        _context.Dispose(); // Ensure resources are properly disposed of
    }
}
```
4. Use Unit of Work in application.
```cs 
public class BlogService
{
    private readonly IUnitOfWork _unitOfWork;

    public BlogService(IUnitOfWork unitOfWork)
    {
        _unitOfWork = unitOfWork;
    }

    public void CreatePostWithComment(Post post, Comment comment)
    {
        _unitOfWork.Posts.Add(post);
        _unitOfWork.Comments.Add(comment);
        
        _unitOfWork.Save(); // Commit the transaction, saving both Post and Comment
    }
}
```
## Entity

An Entity is a business object that typically corresponds to a 
database table in a relational database.

### Repositories

A repository is a service or an object that interacts with the database.
