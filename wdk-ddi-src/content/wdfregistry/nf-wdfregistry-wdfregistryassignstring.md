---
UID: NF:wdfregistry.WdfRegistryAssignString
title: WdfRegistryAssignString function (wdfregistry.h)
description: The WdfRegistryAssignString method assigns a string to a specified value name in the registry. The string is contained in a specified framework string object.
old-location: wdf\wdfregistryassignstring.htm
tech.root: wdf
ms.assetid: e84ee541-4347-4385-9742-5cc0c6c5017f
ms.date: 02/26/2018
keywords: ["WdfRegistryAssignString function"]
ms.keywords: DFRegKeyObjectRef_6b8641ef-885d-47f5-ad8b-afdd57a75c84.xml, WdfRegistryAssignString, WdfRegistryAssignString method, kmdf.wdfregistryassignstring, wdf.wdfregistryassignstring, wdfregistry/WdfRegistryAssignString
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfRegistryAssignString
 - wdfregistry/WdfRegistryAssignString
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
 - WdfRegistryAssignString
---

# WdfRegistryAssignString function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRegistryAssignString</b> method assigns a string to a specified value name in the registry. The string is contained in a specified framework string object.

## -parameters

### -param Key 

[in]
A handle to a registry-key object that represents an opened registry key.

### -param ValueName 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a value name.

### -param String 

[in]
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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryassignstring">WdfRegistryAssignString</a> was not called at IRQL = PASSIVE_LEVEL. 

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
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

If the value name that the <i>ValueName</i> parameter specifies already exists, <b>WdfRegistryAssignString</b> updates the value's data.

The framework sets the value's data type to REG_SZ.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example creates a string object that contains the string "String1" and assigns the string to the <b>ValueName</b> value, under a specified registry key.

```cpp
WDFSTRING string1;
UNICODE_STRING ustring1, valueName;
NTSTATUS status;

RtlInitUnicodeString(
                     &ustring1,
                     L"String1"
                     );
RtlInitUnicodeString(
                     &valueName,
                     L"ValueName"
                     );

status = WdfStringCreate(
                         &ustring1,
                         WDF_NO_OBJECT_ATTRIBUTES,
                         &string1
                         );
if (NT_SUCCESS(status)) {
    status = WdfRegistryAssignString(
                                     Key,
                                     &valueName,
                                     string1
                                     );
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitunicodestring">RtlInitUnicodeString</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryassignmemory">WdfRegistryAssignMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryassignmultistring">WdfRegistryAssignMultiString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryassignulong">WdfRegistryAssignULong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryassignunicodestring">WdfRegistryAssignUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryassignvalue">WdfRegistryAssignValue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfstring/nf-wdfstring-wdfstringcreate">WdfStringCreate</a>

