---
date: 2016-04-09T16:50:16+02:00
title: Client Extension
layout: single
pre: "<b>3. </b>"
weight: 15
---

The Client Extension is a way to expand the base DirectScale Platform functionality. It's a template of sorts made of C# files stored in a GitHub repository. Whenever base code runs, it looks at the Extension to see if any custom code overrides or changes it. The main way this communication occurs is through [Hooks](https://developers.directscale.com/docs/extension-hooks-reference-1).

The client must request access to the Extension. Find out how in the Help Center: [Gaining Access to the Client Extension](https://help.directscale.com/hc/en-us/articles/360047578614-Gaining-Access-to-and-Using-the-Client-Extension).

In the Extension, two important elements must be there:

- A [Solution](https://docs.microsoft.com/en-us/visualstudio/ide/solutions-and-projects-in-visual-studio?view=vs-2019#solutions) named after the client key (client ID). 

    The Client ID is the same as the instance name in the Platform URL: **{Client_ID}**.admin.directscale.com.
- The `ExtentionEntry.cs` file. The base code looks for this file when it tries to discover what type of custom code you've created. Register any code you write or Hooks you use in this file.

---
---

## ConfigureServices()

In `ExtensionEntry.cs`, the `ConfigureServices()` function is the entry method of the Extension. Nothing will run without anything registered within it:

```cs 
public class ExtensionEntry : IExtension
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Include service registrations here.    
     }
}
```

For example, when registering an API endpoint:

```cs
public class ExtensionEntry : IExtension
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddSingleton<IApiEndpoint, ApiExample>();
    }
}
```

---
---

## Assembly Versions

There are two assemblies with specific, required versions:

- [`Microsoft.Extensions.DependencyInjection.Abstractions`](https://www.nuget.org/packages/Microsoft.Extensions.DependencyInjection.Abstractions/2.1.1) (*Version 2.1.1*)
- [`Newtonsoft.Json`](https://github.com/JamesNK/Newtonsoft.Json/releases/tag/12.0.1) (*Version 12.0.1*)

>⚠ You must not update these packages. If you load other versions, the Extension will not work as intended.

---

The rest of the Extension can be set up and structured in your own way.
