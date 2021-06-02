# dataprotection_filesystem

Project does not contains all the files necessarry to run it. 

But the files can be generated by **dotnet new mvc** command

DataProtection keys saving to custom local file system example.

csproj file contains necessary libraries to connect to blob storage.
They might need to be installed by running **dotnet restore** 

So after running this project by **dotnet run**, you will see new xml file inside the keys directory of your project 

You can also apply keys protection with certificate or with dpapi

https://docs.microsoft.com/en-us/aspnet/core/security/data-protection/configuration/overview?view=aspnetcore-5.0#protectkeyswithazurekeyvault
https://jakeydocs.readthedocs.io/en/latest/security/data-protection/configuration/overview.html


services.AddDataProtection()
 .PersistKeysToFileSystem(new DirectoryInfo("keys"))
 .ProtectKeysWithCertificate(cert);
 
https://cdn-6.code-maze.com/data-protection-aspnet-core/

 services.AddDataProtection()
 .PersistKeysToFileSystem(new DirectoryInfo("keys"))
 .ProtectKeysWithDpapi();
 
 I just didn't test keys protection but persisting works fine (tested both on local and on azure app service) 
