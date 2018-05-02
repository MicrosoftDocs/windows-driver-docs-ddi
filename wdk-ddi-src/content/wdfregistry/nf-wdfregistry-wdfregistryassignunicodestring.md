---
UID: NF:wdfregistry.WdfRegistryAssignUnicodeString
title: WdfRegistryAssignUnicodeString function
author: windows-driver-content
description: The WdfRegistryAssignUnicodeString method assigns a specified Unicode string to a specified value name in the registry.
old-location: wdf\wdfregistryassignunicodestring.htm
old-project: wdf
ms.assetid: 3a614b58-8230-4137-aae9-5c50e94bea5e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRegKeyObjectRef_83d456aa-06de-47c9-94df-b5b9684a95ac.xml, WdfRegistryAssignUnicodeString, WdfRegistryAssignUnicodeString method, kmdf.wdfregistryassignunicodestring, wdf.wdfregistryassignunicodestring, wdfregistry/WdfRegistryAssignUnicodeString
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
-	WdfRegistryAssignUnicodeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRegistryAssignUnicodeString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryAssignUnicodeString</b> method assigns a specified Unicode string to a specified value name in the registry.


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains a value name. 


### -param Value [in]

A pointer to a UNICODE_STRING structure that contains the string to be assigned to the value name that <i>ValueName</i> specifies.


## -returns



<b>WdfRegistryAssignUnicodeString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549912">WdfRegistryAssignUnicodeString</a> was not called at IRQL = PASSIVE_LEVEL. 

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
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If the string that the <i>Value</i> parameter specifies is not NULL-terminated, the framework adds a NULL character when copying the string to the registry.

If the value name that the <i>ValueName</i> parameter specifies already exists, <b>WdfRegistryAssignUnicodeString</b> updates the value's data.

The framework sets the value's data type to REG_SZ.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example assigns a Unicode string "String1" to the <b>ValueName</b> value, under a specified registry key.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>UNICODE_STRING ustring1, valueName;
NTSTATUS status;

RtlInitUnicodeString(
                     &amp;ustring1,
                     L"String1"
                     );
RtlInitUnicodeString(
                     &amp;valueName,
                     L"ValueName"
                     );

status = WdfRegistryAssignUnicodeString(
                                        Key,
                                        &amp;valueName,
                                        &amp;string1
                                        );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561934">RtlInitUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549901">WdfRegistryAssignMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549903">WdfRegistryAssignMultiString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549906">WdfRegistryAssignString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549910">WdfRegistryAssignULong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549913">WdfRegistryAssignValue</a>
 

 

