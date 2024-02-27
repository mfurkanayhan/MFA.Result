# MFA.Result

## Overview
`MFA.Result` is a lightweight, versatile .NET library designed to simplify error handling and response management in your applications. It provides a robust way to encapsulate the results of operations, including success or failure information along with data and error messages. This library is ideal for APIs, web applications, and any .NET project that requires clear and concise result management.

## Features
- Generic `Result<T>` class to handle operation outcomes with success or failure states.
- Support for HTTP status codes to align with RESTful API response patterns.
- Implicit conversion operators for easy construction of `Result` objects.
- Optional error messages list for detailed failure information.

## Installation

To install `MFA.Result`, use the NuGet Package Manager console:

Installation of `MFA.Result` can be done using several methods as described below. Choose the one that best fits your development environment and workflow.

### Using NuGet Package Manager Console

To install `MFA.Result` via the NuGet Package Manager Console in Visual Studio, use the following command:

```powershell 
Install-Package MFA.Result -Version 8.0.0
```

### Using NuGet CLI

If you prefer using the command line, NuGet CLI can be used to install `MFA.Result`. First, ensure you have the NuGet CLI installed, then run the following command:

```powershell
nuget install MFA.Result -Version 8.0.0
```

### Using Visual Studio's NuGet Package Manager GUI

For those who prefer a graphical interface within Visual Studio:
1.  Open your solution in Visual Studio.
2.  Right-click on your project in the Solution Explorer and select `Manage NuGet Packages`.
3.  Go to the `Browse` tab, search for `MFA.Result`, select it, then press `Install`.
4.  Choose the version you wish to install if prompted.

These methods provide flexibility in how you can add `MFA.Result` to your projects, depending on your preference for tooling and the environment.
## Usage
Below are some examples of how to use the `MFA.Result` library in your projects.

### Successful Operation
```csharp
public Result<string> GetUserName(int userId)
{
    // Your logic here
    return "John Doe"; // Implicitly converts to a successful Result
}
```
### Operation With Error
```csharp
public Result<string> GetUserName(int userId)
{
    // Your logic here
    return (HttpStatusCode.NotFound, "User not found");
}
```
### Checking Operation Result
```csharp
var result = GetUserName(1);
if (result.IsSuccessful)
{
    Console.WriteLine(result.Data);
}
else
{
    Console.WriteLine(result.ErrorMessages.FirstOrDefault());
}
```
## Contributing
Contributions are welcome! If you have suggestions or want to improve `MFA.Result`, please feel free to fork the repository, make changes, and submit a pull request.
## License
`MFA.Result` is available under the MIT license. See the LICENSE file for more info.
## Contact
For any questions or feedback, please contact Muhammet Furkan Ayhan at mfurkana067@gmail.com