---
UID: NF:wdfregistry.WdfRegistryQueryMemory
title: WdfRegistryQueryMemory function (wdfregistry.h)
description: The WdfRegistryQueryMemory method retrieves the data that is currently assigned to a specified registry value, stores the data in a framework-allocated buffer, and creates a framework memory object to represent the buffer.
old-location: wdf\wdfregistryquerymemory.htm
tech.root: wdf
ms.assetid: 2d689ede-418e-4bf3-8c0e-82ded1085382
ms.date: 02/26/2018
keywords: ["WdfRegistryQueryMemory function"]
ms.keywords: DFRegKeyObjectRef_97e02e2b-59d4-4041-a22d-e3a8905c096f.xml, WdfRegistryQueryMemory, WdfRegistryQueryMemory method, kmdf.wdfregistryquerymemory, wdf.wdfregistryquerymemory, wdfregistry/WdfRegistryQueryMemory
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
 - WdfRegistryQueryMemory
 - wdfregistry/WdfRegistryQueryMemory
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
 - WdfRegistryQueryMemory
---

# WdfRegistryQueryMemory function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRegistryQueryMemory</b> method retrieves the data that is currently assigned to a specified registry value, stores the data in a framework-allocated buffer, and creates a framework memory object to represent the buffer.

## -parameters

### -param Key 

[in]
A handle to a registry-key object that represents an opened registry key.

### -param ValueName 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a value name.

### -param PoolType 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>-typed value that specifies the type of memory to be allocated for the data buffer.

### -param MemoryAttributes 

[in, optional]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for the new memory object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param Memory 

[out]
A pointer to a location that receives a handle to the new memory object.

### -param ValueType 

[out, optional]
A pointer to a location that receives the data type. For a list of data type values, see the <b>Type</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a>. This pointer is optional and can be <b>NULL</b>.

## -returns

<b>WdfRegistryQueryMemory</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryquerymemory">WdfRegistryQueryMemory</a> was not called at IRQL = PASSIVE_LEVEL. 

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
A memory object could not be allocated.

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
 

For a list of other return values that the <b>WdfRegistryQueryMemory</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.



This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

When a driver calls <b>WdfRegistryQueryMemory</b>, the framework allocates a buffer that is large enough to hold the specified registry value's data. After <b>WdfRegistryQueryMemory</b> returns, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a> to obtain a pointer to the buffer and the buffer's size.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example retrieves the data that is assigned to the <b>MyValueName</b> value and then obtains the data's address and size.

```cpp
WDFMEMORY memory;
size_t size;
PUCHAR pBuf;
NTSTATUS status;
ULONG type;
DECLARE_CONST_UNICODE_STRING(valueName1, L"MyValueName");

status = WdfRegistryQueryMemory(
                                Key,
                                &valueName1,
                                PagedPool,
                                NULL,
                                &memory,
                                &type
                                );
pBuf = (PUCHAR)WdfMemoryGetBuffer(
                                   memory,
                                   &size
                                   );
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryquerymultistring">WdfRegistryQueryMultiString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryquerystring">WdfRegistryQueryString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryqueryulong">WdfRegistryQueryULong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryqueryunicodestring">WdfRegistryQueryUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryqueryvalue">WdfRegistryQueryValue</a>

