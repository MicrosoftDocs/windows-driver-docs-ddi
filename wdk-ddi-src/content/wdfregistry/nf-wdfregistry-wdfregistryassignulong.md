---
UID: NF:wdfregistry.WdfRegistryAssignULong
title: WdfRegistryAssignULong function (wdfregistry.h)
description: The WdfRegistryAssignULong method assigns a specified unsigned long word value to a specified value name in the registry.
old-location: wdf\wdfregistryassignulong.htm
tech.root: wdf
ms.assetid: a5a160a7-3408-4d26-83c8-2f5a7b6acaf1
ms.date: 02/26/2018
ms.keywords: DFRegKeyObjectRef_2f35ea01-ade1-4bf1-a55b-6613021fcd04.xml, WdfRegistryAssignULong, WdfRegistryAssignULong method, kmdf.wdfregistryassignulong, wdf.wdfregistryassignulong, wdfregistry/WdfRegistryAssignULong
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfRegistryAssignULong
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRegistryAssignULong function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRegistryAssignULong</b> method assigns a specified unsigned long word value to a specified value name in the registry.


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a value name. 


### -param Value [in]

A ULONG value that will be assigned to the value name that <i>ValueName</i> specifies.


## -returns



<b>WdfRegistryAssignULong</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549910">WdfRegistryAssignULong</a> was not called at IRQL = PASSIVE_LEVEL. 

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



If the value name that the <i>ValueName</i> parameter specifies already exists, <b>WdfRegistryAssignULong</b> updates the value's data.

The framework sets the value's data type to REG_DWORD.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example assigns the constant MY_VALUE to the <b>ValueName</b> value, under a specified registry key.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>UNICODE_STRING valueName;
NTSTATUS status;

RtlInitUnicodeString(
                     &valueName,
                     L"ValueName"
                     );
status = WdfRegistryAssignULong(
                                Key,
                                &valueName,
                                MY_VALUE
                                );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549901">WdfRegistryAssignMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549903">WdfRegistryAssignMultiString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549906">WdfRegistryAssignString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549912">WdfRegistryAssignUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549913">WdfRegistryAssignValue</a>
 

 

