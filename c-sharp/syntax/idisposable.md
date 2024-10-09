# `IDisposable`

`IDisposable` interface provides a mechanism to release unmanaged resources explicitly when they are no longer needed. Unmanaged resources are resources not handled by the .NET runtime's garbage collector, such as file handles, network connections, or database connections.

## Example
```cs
using System;
using System.IO;

public class FileManager : IDisposable
{
    private FileStream _fileStream;
    private bool _disposed = false;

    public FileManager(string filePath)
    {
        _fileStream = new FileStream(filePath, FileMode.OpenOrCreate);
    }

    // Example method that writes to the file
    public void WriteToFile(string content)
    {
        if (_disposed)
            throw new ObjectDisposedException(nameof(FileManager));

        using (StreamWriter writer = new StreamWriter(_fileStream))
        {
            writer.WriteLine(content);
        }
    }

    // Implementation of IDisposable
    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this); // Prevent finalizer from running since the resources are already released
    }

    protected virtual void Dispose(bool disposing)
    {
        if (!_disposed)
        {
            if (disposing)
            {
                // Free managed resources here, if any
                if (_fileStream != null)
                {
                    _fileStream.Close();
                    _fileStream = null;
                }
            }

            // Free unmanaged resources here, if any

            _disposed = true;
        }
    }

    // Finalizer (in case Dispose was not called explicitly)
    ~FileManager()
    {
        Dispose(false);
    }
}
```

And the class in action:
```cs
public static void Main(string[] args)
{
    using (var fileManager = new FileManager("example.txt"))
    {
        fileManager.WriteToFile("Hello, IDisposable!");
    } // Dispose() is automatically called here
}
```