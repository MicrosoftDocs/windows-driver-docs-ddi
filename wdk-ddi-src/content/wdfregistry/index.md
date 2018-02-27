---
UID: NA:wdfregistry
ms.assetid: 9925a60e-abc4-3a3b-b2a7-f7d9c91498e1
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfregistry.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfregistry.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WdfRegistryAssignMemory function](nf-wdfregistry-wdfregistryassignmemory.md) | The WdfRegistryAssignMemory method assigns data that is contained in a specified memory buffer to a specified value name in the registry. |
| [WdfRegistryAssignMultiString function](nf-wdfregistry-wdfregistryassignmultistring.md) | The WdfRegistryAssignMultiString method assigns a set of strings to a specified value name in the registry. The strings are contained in a specified collection of framework string objects. |
| [WdfRegistryAssignString function](nf-wdfregistry-wdfregistryassignstring.md) | The WdfRegistryAssignString method assigns a string to a specified value name in the registry. The string is contained in a specified framework string object. |
| [WdfRegistryAssignULong function](nf-wdfregistry-wdfregistryassignulong.md) | The WdfRegistryAssignULong method assigns a specified unsigned long word value to a specified value name in the registry. |
| [WdfRegistryAssignUnicodeString function](nf-wdfregistry-wdfregistryassignunicodestring.md) | The WdfRegistryAssignUnicodeString method assigns a specified Unicode string to a specified value name in the registry. |
| [WdfRegistryAssignValue function](nf-wdfregistry-wdfregistryassignvalue.md) | The WdfRegistryAssignValue method assigns specified data to a specified value name in the registry. |
| [WdfRegistryClose function](nf-wdfregistry-wdfregistryclose.md) | The WdfRegistryClose method closes the registry key that is associated with a specified framework registry-key object and then deletes the registry-key object. |
| [WdfRegistryCreateKey function](nf-wdfregistry-wdfregistrycreatekey.md) | The WdfRegistryCreateKey method creates and opens a specified registry key, or just opens the key if it already exists, and creates a framework registry-key object that represents the registry key. |
| [WdfRegistryOpenKey function](nf-wdfregistry-wdfregistryopenkey.md) | The WdfRegistryOpenKey method opens a specified registry key and creates a framework registry-key object that represents the registry key. |
| [WdfRegistryQueryMemory function](nf-wdfregistry-wdfregistryquerymemory.md) | The WdfRegistryQueryMemory method retrieves the data that is currently assigned to a specified registry value, stores the data in a framework-allocated buffer, and creates a framework memory object to represent the buffer. |
| [WdfRegistryQueryMultiString function](nf-wdfregistry-wdfregistryquerymultistring.md) | The WdfRegistryQueryMultiString method retrieves the strings that are currently assigned to a specified multi-string registry value, creates a framework string object for each string, and adds each string object to a specified object collection. |
| [WdfRegistryQueryString function](nf-wdfregistry-wdfregistryquerystring.md) | The WdfRegistryQueryString method retrieves the string data that is currently assigned to a specified registry string value and assigns the string to a specified framework string object. |
| [WdfRegistryQueryULong function](nf-wdfregistry-wdfregistryqueryulong.md) | The WdfRegistryQueryULong method retrieves the unsigned long word (REG_DWORD) data that is currently assigned to a specified registry value and copies the data to a specified location. |
| [WdfRegistryQueryUnicodeString function](nf-wdfregistry-wdfregistryqueryunicodestring.md) | The WdfRegistryQueryUnicodeString method retrieves the string data that is currently assigned to a specified registry string value and copies the string to a specified UNICODE_STRING structure. |
| [WdfRegistryQueryValue function](nf-wdfregistry-wdfregistryqueryvalue.md) | The WdfRegistryQueryValue method retrieves the data that is currently assigned to a specified registry value. |
| [WdfRegistryRemoveKey function](nf-wdfregistry-wdfregistryremovekey.md) | The WdfRegistryRemoveKey method removes the registry key that is associated with a specified framework registry-key object and then deletes the registry-key object. |
| [WdfRegistryRemoveValue function](nf-wdfregistry-wdfregistryremovevalue.md) | The WdfRegistryRemoveValue method removes a specified value and its data from a specified registry key. |
| [WdfRegistryWdmGetHandle function](nf-wdfregistry-wdfregistrywdmgethandle.md) | The WdfRegistryWdmGetHandle method returns a Windows Driver Model (WDM) handle to the registry key that a specified framework registry-key object represents. |
