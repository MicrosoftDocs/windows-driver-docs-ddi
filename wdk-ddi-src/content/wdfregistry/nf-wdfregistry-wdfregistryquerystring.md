---
UID: NF:wdfregistry.WdfRegistryQueryString
title: WdfRegistryQueryString function
author: windows-driver-content
description: The WdfRegistryQueryString method retrieves the string data that is currently assigned to a specified registry string value and assigns the string to a specified framework string object.
old-location: wdf\wdfregistryquerystring.htm
old-project: wdf
ms.assetid: 2c1242ea-5d77-464e-9203-ef2236ea4619
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFRegKeyObjectRef_d3260d42-afdc-4858-a0b4-e2ae90327066.xml, WdfRegistryQueryString method, WdfRegistryQueryString, wdf.wdfregistryquerystring, wdfregistry/WdfRegistryQueryString, kmdf.wdfregistryquerystring
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
-	WdfRegistryQueryString
product: Windows
targetos: Windows
req.typenames: "*PWDF_QUERY_INTERFACE_CONFIG, WDF_QUERY_INTERFACE_CONFIG"
req.product: Windows 10 or later.
---

# WdfRegistryQueryString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryQueryString</b> method retrieves the string data that is currently assigned to a specified registry string value and assigns the string to a specified framework string object.


## -syntax


````
NTSTATUS WdfRegistryQueryString(
  _In_ WDFKEY           Key,
  _In_ PCUNICODE_STRING ValueName,
  _In_ WDFSTRING        String
);
````


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a name for the registry value. 


### -param String [in]

A handle to a framework string object. The framework will assign the registry value's string data to this object.


## -returns


<b>WdfRegistryQueryString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:
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

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerystring.md">WdfRegistryQueryString</a> was not called at IRQL = PASSIVE_LEVEL. 

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
There was insufficient memory to complete the operation.

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
The data type of the registry value that the <i>ValueName</i> parameter specified was not REG_SZ.

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

For a list of other return values that the <b>WdfRegistryQueryString</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


To obtain a string from a string object, your driver can call <a href="..\wdfstring\nf-wdfstring-wdfstringgetunicodestring.md">WdfStringGetUnicodeString</a>. 

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.



## -see-also

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerymemory.md">WdfRegistryQueryMemory</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryvalue.md">WdfRegistryQueryValue</a>

<a href="..\wdfstring\nf-wdfstring-wdfstringcreate.md">WdfStringCreate</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerymultistring.md">WdfRegistryQueryMultiString</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryulong.md">WdfRegistryQueryULong</a>

<a href="..\wdfstring\nf-wdfstring-wdfstringgetunicodestring.md">WdfStringGetUnicodeString</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryunicodestring.md">WdfRegistryQueryUnicodeString</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryQueryString method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

