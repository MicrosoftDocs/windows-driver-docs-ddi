---
UID: NF:wdfregistry.WdfRegistryQueryULong
title: WdfRegistryQueryULong function
author: windows-driver-content
description: The WdfRegistryQueryULong method retrieves the unsigned long word (REG_DWORD) data that is currently assigned to a specified registry value and copies the data to a specified location.
old-location: wdf\wdfregistryqueryulong.htm
old-project: wdf
ms.assetid: 54583406-9c60-4622-a78d-085c35ce7593
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFRegKeyObjectRef_537593c8-1f9c-4392-9228-6a0e5d89a964.xml, WdfRegistryQueryULong, WdfRegistryQueryULong method, kmdf.wdfregistryqueryulong, wdf.wdfregistryqueryulong, wdfregistry/WdfRegistryQueryULong
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
-	WdfRegistryQueryULong
product: Windows
targetos: Windows
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# WdfRegistryQueryULong function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryQueryULong</b> method retrieves the unsigned long word (REG_DWORD) data that is currently assigned to a specified registry value and copies the data to a specified location.


## -syntax


````
NTSTATUS WdfRegistryQueryULong(
  _In_  WDFKEY           Key,
  _In_  PCUNICODE_STRING ValueName,
  _Out_ PULONG           Value
);
````


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a name for the registry value. 


### -param Value [out]

A pointer to a location that receives the data that is assigned to the registry value that <i>ValueName</i> specifies.


## -returns



<b>WdfRegistryQueryULong</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryulong.md">WdfRegistryQueryULong</a> was not called at IRQL = PASSIVE_LEVEL. 

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
The data type of the registry value that the <i>ValueName</i> parameter specified was not REG_DWORD.

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
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about registry-key objects, see <a href="https://msdn.microsoft.com/278a5ccb-dd43-4b26-999f-9207a4ede9dc">Using the Registry in WDF Drivers</a>.


#### Examples

The following code example retrieves the data that is currently assigned to the <b>NumberOfThings</b> value.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status;
ULONG  value;
DECLARE_CONST_UNICODE_STRING(valueName, L"NumberOfThings");

status = WdfRegistryQueryULong(
                               hKey,
                               &amp;valueName,
                               &amp;value
                               );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryunicodestring.md">WdfRegistryQueryUnicodeString</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerymemory.md">WdfRegistryQueryMemory</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryvalue.md">WdfRegistryQueryValue</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerystring.md">WdfRegistryQueryString</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerymultistring.md">WdfRegistryQueryMultiString</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryQueryULong method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

