This is an example on how to create new WMI Classes in CMD or Replace Existing ones.

First create your .mof file from the template https://learn.microsoft.com/en-us/windows/win32/wmisdk/creating-a-base-class.
Then run mofcomp -N:root\wmi "PathToYourMof" to replace or create new WMI Class.
