---
UID: NF:wdfregistry.WdfRegistryAssignValue
title: WdfRegistryAssignValue function
author: windows-driver-content
description: The WdfRegistryAssignValue method assigns specified data to a specified value name in the registry.
old-location: wdf\wdfregistryassignvalue.htm
old-project: wdf
ms.assetid: 3c7592ad-f4ed-496f-90bb-638f68efe4f7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRegKeyObjectRef_b585a896-046f-4730-8f1d-bba4a2479772.xml, WdfRegistryAssignValue, WdfRegistryAssignValue method, kmdf.wdfregistryassignvalue, wdf.wdfregistryassignvalue, wdfregistry/WdfRegistryAssignValue
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
-	WdfRegistryAssignValue
product: Windows
targetos: Windows
req.typenames: 
---

# WdfRegistryAssignValue function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryAssignValue</b> method assigns specified data to a specified value name in the registry.


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains a value name. 


### -param ValueType [in]

A value that identifies the data type. For a list of data type values, see the <b>Type</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff553410">KEY_VALUE_BASIC_INFORMATION</a>.


### -param ValueLength [in]

The length, in bytes, of the buffer that <i>Value</i> points to.


### -param Value [in]

A pointer to a buffer that contains driver-supplied data.


## -returns



<b>WdfRegistryAssignValue</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549913">WdfRegistryAssignValue</a> was not called at IRQL = PASSIVE_LEVEL. 

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



If the value name that the <i>ValueName</i> parameter specifies already exists, <b>WdfRegistryAssignValue</b> updates the value's data.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example assigns hexadecimal 123456 to a registry value as binary data.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ULONG val;
NTSTATUS status;

val = 0x123456;
status = WdfRegistryAssignValue(
                                Key,
                                &amp;valueName,
                                REG_BINARY,
                                sizeof(val),
                                &amp;val
                                );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553410">KEY_VALUE_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549901">WdfRegistryAssignMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549903">WdfRegistryAssignMultiString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549906">WdfRegistryAssignString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549910">WdfRegistryAssignULong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549912">WdfRegistryAssignUnicodeString</a>
 

 

