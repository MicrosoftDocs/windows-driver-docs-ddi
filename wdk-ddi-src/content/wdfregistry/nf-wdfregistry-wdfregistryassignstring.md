---
UID: NF:wdfregistry.WdfRegistryAssignString
title: WdfRegistryAssignString function
author: windows-driver-content
description: The WdfRegistryAssignString method assigns a string to a specified value name in the registry. The string is contained in a specified framework string object.
old-location: wdf\wdfregistryassignstring.htm
old-project: wdf
ms.assetid: e84ee541-4347-4385-9742-5cc0c6c5017f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRegKeyObjectRef_6b8641ef-885d-47f5-ad8b-afdd57a75c84.xml, WdfRegistryAssignString, WdfRegistryAssignString method, kmdf.wdfregistryassignstring, wdf.wdfregistryassignstring, wdfregistry/WdfRegistryAssignString
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
-	WdfRegistryAssignString
product: Windows
targetos: Windows
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# WdfRegistryAssignString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryAssignString</b> method assigns a string to a specified value name in the registry. The string is contained in a specified framework string object.


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains a value name. 


### -param String [in]

A handle to a framework string object that contains a string. 


## -returns



<b>WdfRegistryAssignString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549906">WdfRegistryAssignString</a> was not called at IRQL = PASSIVE_LEVEL. 

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
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The driver did not open the registry key with KEY_SET_VALUE access.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If the value name that the <i>ValueName</i> parameter specifies already exists, <b>WdfRegistryAssignString</b> updates the value's data.

The framework sets the value's data type to REG_SZ.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example creates a string object that contains the string "String1" and assigns the string to the <b>ValueName</b> value, under a specified registry key.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFSTRING string1;
UNICODE_STRING ustring1, valueName;
NTSTATUS status;

RtlInitUnicodeString(
                     &amp;ustring1,
                     L"String1"
                     );
RtlInitUnicodeString(
                     &amp;valueName,
                     L"ValueName"
                     );

status = WdfStringCreate(
                         &amp;ustring1,
                         WDF_NO_OBJECT_ATTRIBUTES,
                         &amp;string1
                         );
if (NT_SUCCESS(status)) {
    status = WdfRegistryAssignString(
                                     Key,
                                     &amp;valueName,
                                     string1
                                     );
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561934">RtlInitUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549901">WdfRegistryAssignMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549903">WdfRegistryAssignMultiString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549910">WdfRegistryAssignULong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549912">WdfRegistryAssignUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549913">WdfRegistryAssignValue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550046">WdfStringCreate</a>
 

 

