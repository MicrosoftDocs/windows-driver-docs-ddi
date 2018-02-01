---
UID: NF:wdfregistry.WdfRegistryQueryMultiString
title: WdfRegistryQueryMultiString function
author: windows-driver-content
description: The WdfRegistryQueryMultiString method retrieves the strings that are currently assigned to a specified multi-string registry value, creates a framework string object for each string, and adds each string object to a specified object collection.
old-location: wdf\wdfregistryquerymultistring.htm
old-project: wdf
ms.assetid: 9ce754b4-a783-4b2e-978d-e38a30c5d3dd
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfregistryquerymultistring, DFRegKeyObjectRef_9610d27f-df2e-41f9-9376-4f5819e8ce66.xml, WdfRegistryQueryMultiString, wdfregistry/WdfRegistryQueryMultiString, WdfRegistryQueryMultiString method, kmdf.wdfregistryquerymultistring
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfRegistryQueryMultiString
product: Windows
targetos: Windows
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# WdfRegistryQueryMultiString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryQueryMultiString</b> method retrieves the strings that are currently assigned to a specified multi-string registry value, creates a framework string object for each string, and adds each string object to a specified <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-collections">object collection</a>.


## -syntax


````
NTSTATUS WdfRegistryQueryMultiString(
  _In_     WDFKEY                 Key,
  _In_     PCUNICODE_STRING       ValueName,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES StringsAttributes,
  _In_     WDFCOLLECTION          Collection
);
````


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a value name. 


### -param StringsAttributes [in, optional]

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for each new string object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES. 


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

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerymultistring.md">WdfRegistryQueryMultiString</a> was not called at IRQL = PASSIVE_LEVEL. 

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


Before your driver calls <b>WdfRegistryQueryMultiString</b>, it must call <a href="..\wdfcollection\nf-wdfcollection-wdfcollectioncreate.md">WdfCollectionCreate</a> to create a collection object. 

After <b>WdfRegistryQueryMultiString</b> returns, the driver can call <a href="..\wdfcollection\nf-wdfcollection-wdfcollectiongetcount.md">WdfCollectionGetCount</a> to obtain the number of retrieved strings and <a href="..\wdfcollection\nf-wdfcollection-wdfcollectiongetitem.md">WdfCollectionGetItem</a> to obtain string objects from the collection.

If the collection contains objects before the driver calls the <b>WdfRegistryQueryMultiString</b> method, the method does not remove those objects or change their index values. The new objects are appended to the end of the collection.

To obtain a string from a string object, the driver can call <a href="..\wdfstring\nf-wdfstring-wdfstringgetunicodestring.md">WdfStringGetUnicodeString</a>. 

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.



## -see-also

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryulong.md">WdfRegistryQueryULong</a>

<a href="..\wdfcollection\nf-wdfcollection-wdfcollectioncreate.md">WdfCollectionCreate</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryvalue.md">WdfRegistryQueryValue</a>

<a href="..\wdfstring\nf-wdfstring-wdfstringgetunicodestring.md">WdfStringGetUnicodeString</a>

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerymemory.md">WdfRegistryQueryMemory</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerystring.md">WdfRegistryQueryString</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryunicodestring.md">WdfRegistryQueryUnicodeString</a>

<a href="..\wdfcollection\nf-wdfcollection-wdfcollectiongetcount.md">WdfCollectionGetCount</a>

<a href="..\wdfcollection\nf-wdfcollection-wdfcollectiongetitem.md">WdfCollectionGetItem</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryQueryMultiString method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

