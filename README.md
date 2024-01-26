This is an example on how to create new WMI Classes in CMD or Replace Existing ones.

First create your .mof file from the template https://learn.microsoft.com/en-us/windows/win32/wmisdk/creating-a-base-class.
Then run mofcomp -N:root\wmi "PathToYourMof" to replace or create new WMI Class.

This is just a minimal version of the WMI Class. If you want to replace the existing one with real values you would need to adjust this fields below to the WMI Class standard in the link above:
PS C:\WINDOWS\system32> Get-CimClass -ClassName WmiMonitorID -Namespace root\wmi | Select -ExpandProperty CimClassProperties
