---
UID: NF:wdfregistry.WdfRegistryQueryMultiString
title: WdfRegistryQueryMultiString function
author: windows-driver-content
description: The WdfRegistryQueryMultiString method retrieves the strings that are currently assigned to a specified multi-string registry value, creates a framework string object for each string, and adds each string object to a specified object collection.
old-location: wdf\wdfregistryquerymultistring.htm
tech.root: wdf
ms.assetid: 9ce754b4-a783-4b2e-978d-e38a30c5d3dd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRegKeyObjectRef_9610d27f-df2e-41f9-9376-4f5819e8ce66.xml, WdfRegistryQueryMultiString, WdfRegistryQueryMultiString method, kmdf.wdfregistryquerymultistring, wdf.wdfregistryquerymultistring, wdfregistry/WdfRegistryQueryMultiString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfregistry.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfRegistryQueryMultiString
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRegistryQueryMultiString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRegistryQueryMultiString</b> method retrieves the strings that are currently assigned to a specified multi-string registry value, creates a framework string object for each string, and adds each string object to a specified <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-collections">object collection</a>.


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains a value name. 


### -param StringsAttributes [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for each new string object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES. 


### -param Collection [in]

A handle to a driver-supplied framework collection object.


## -returns



<b>WdfRegistryQueryMultiString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549921">WdfRegistryQueryMultiString</a> was not called at IRQL = PASSIVE_LEVEL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A string object could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The driver did not open the registry key with KEY_QUERY_VALUE, KEY_READ, or KEY_ALL_ACCESS access.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The data type of the registry value that the <i>ValueName</i> parameter specified was not REG_MULTI_SZ.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The registry value was not available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RESOURCE_DATA_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The registry value exists under the specified key, but is empty. 

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfRegistryQueryMultiString</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Before your driver calls <b>WdfRegistryQueryMultiString</b>, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545747">WdfCollectionCreate</a> to create a collection object. 

After <b>WdfRegistryQueryMultiString</b> returns, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545759">WdfCollectionGetCount</a> to obtain the number of retrieved strings and <a href="https://msdn.microsoft.com/library/windows/hardware/ff545770">WdfCollectionGetItem</a> to obtain string objects from the collection.

If the collection contains objects before the driver calls the <b>WdfRegistryQueryMultiString</b> method, the method does not remove those objects or change their index values. The new objects are appended to the end of the collection.

To obtain a string from a string object, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550049">WdfStringGetUnicodeString</a>. 

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example creates a collection object, initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure so that the collection object will be the parent of all of the string objects that the framework creates for the collection, and retrieves the strings from a multi-string registry value. Finally, the example obtains the number of string objects that the framework added to the collection.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES stringAttributes;
WDFCOLLECTION col;
NTSTATUS status;
ULONG count;
DECLARE_CONST_UNICODE_STRING(valueMultiSz, VALUE_MULTI_SZ);

status = WdfCollectionCreate(
                             NULL,
                             &amp;col
                             );
ASSERT(NT_SUCCESS(status));

WDF_OBJECT_ATTRIBUTES_INIT(&amp;stringAttributes);
stringAttributes.ParentObject = col;

status = WdfRegistryQueryMultiString(
                                     Key,
                                     &amp;valueMultiSzEmpty,
                                     &amp;stringAttributes,
                                     col
                                     );

count = WdfCollectionGetCount(col);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545747">WdfCollectionCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545759">WdfCollectionGetCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545770">WdfCollectionGetItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549920">WdfRegistryQueryMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549923">WdfRegistryQueryString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549925">WdfRegistryQueryULong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549927">WdfRegistryQueryUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549928">WdfRegistryQueryValue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550049">WdfStringGetUnicodeString</a>
 

 

