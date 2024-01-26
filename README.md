This is an example on how to create new WMI Classes in CMD or Replace Existing ones.

First create your .mof file from the template https://learn.microsoft.com/en-us/windows/win32/wmisdk/creating-a-base-class.
Then run mofcomp -N:root\wmi "PathToYourMof" to replace or create new WMI Class.

This is just a minimal version of the WMI Class. If you want to replace the existing one with real values you would need to adjust this fields below to the WMI Class standard in the link above:

PS C:\WINDOWS\system32> Get-CimClass -ClassName WmiMonitorID -Namespace root\wmi | Select -ExpandProperty CimClassProperties


Name               : Active
Value              :
CimType            : Boolean
Flags              : Property, ReadOnly, NullValue
Qualifiers         : {read}
ReferenceClassName :

Name               : InstanceName
Value              :
CimType            : String
Flags              : Property, Key, ReadOnly, NullValue
Qualifiers         : {key, read}
ReferenceClassName :

Name               : ManufacturerName
Value              :
CimType            : UInt16Array
Flags              : Property, ReadOnly, NullValue
Qualifiers         : {MAX, read, WmiDataId}
ReferenceClassName :

Name               : ProductCodeID
Value              :
CimType            : UInt16Array
Flags              : Property, ReadOnly, NullValue
Qualifiers         : {MAX, read, WmiDataId}
ReferenceClassName :

Name               : SerialNumberID
Value              :
CimType            : UInt16Array
Flags              : Property, ReadOnly, NullValue
Qualifiers         : {MAX, read, WmiDataId}
ReferenceClassName :

Name               : UserFriendlyName
Value              :
CimType            : UInt16Array
Flags              : Property, ReadOnly, NullValue
Qualifiers         : {read, WmiDataId, WmiSizeIs}
ReferenceClassName :

Name               : UserFriendlyNameLength
Value              :
CimType            : UInt16
Flags              : Property, ReadOnly, NullValue
Qualifiers         : {read, WmiDataId}
ReferenceClassName :

Name               : WeekOfManufacture
Value              :
CimType            : UInt8
Flags              : Property, ReadOnly, NullValue
Qualifiers         : {read, WmiDataId}
ReferenceClassName :

Name               : YearOfManufacture
Value              :
CimType            : UInt16
Flags              : Property, ReadOnly, NullValue
Qualifiers         : {read, WmiDataId}
ReferenceClassName :

And make the Values look like this:
 Get-WmiObject -Class WmiMonitorID -Namespace root\wmi
 __GENUS                : 2
__CLASS                : WmiMonitorID
__SUPERCLASS           : MSMonitorClass
__DYNASTY              : MSMonitorClass
__RELPATH              : WmiMonitorID.InstanceName="DISPLAY\\SAM0D2C\\4&29c712e5&0&UID214595_0"
__PROPERTY_COUNT       : 9
__DERIVATION           : {MSMonitorClass}
__SERVER               : NT4-ADV
__NAMESPACE            : root\wmi
__PATH                 : \\NT4-ADV\root\wmi:WmiMonitorID.InstanceName="DISPLAY\\SAM0D2C\\4&29c712e5&0&UID214595_0"
Active                 : True
InstanceName           : DISPLAY\SAM0D2C\4&29c712e5&0&UID214595_0
ManufacturerName       : {83, 65, 77, 0...}
ProductCodeID          : {48, 68, 50, 67...}
SerialNumberID         : {72, 52, 90, 77...}
UserFriendlyName       : {67, 50, 52, 70...}
UserFriendlyNameLength : 13
WeekOfManufacture      : 22
YearOfManufacture      : 2019
PSComputerName         : NT4-ADV

__GENUS                : 2
__CLASS                : WmiMonitorID
__SUPERCLASS           : MSMonitorClass
__DYNASTY              : MSMonitorClass
__RELPATH              : WmiMonitorID.InstanceName="DISPLAY\\BNQ7F58\\5&a86ea05&1&UID4357_0"
__PROPERTY_COUNT       : 9
__DERIVATION           : {MSMonitorClass}
__SERVER               : NT4-ADV
__NAMESPACE            : root\wmi
__PATH                 : \\NT4-ADV\root\wmi:WmiMonitorID.InstanceName="DISPLAY\\BNQ7F58\\5&a86ea05&1&UID4357_0"
Active                 : True
InstanceName           : DISPLAY\BNQ7F58\5&a86ea05&1&UID4357_0
ManufacturerName       : {66, 78, 81, 0...}
ProductCodeID          : {55, 70, 53, 56...}
SerialNumberID         : {67, 52, 75, 48...}
UserFriendlyName       : {90, 79, 87, 73...}
UserFriendlyNameLength : 13
WeekOfManufacture      : 16
YearOfManufacture      : 2019
PSComputerName         : NT4-ADV
