---
UID: NF:wdfregistry.WdfRegistryQueryMemory
title: WdfRegistryQueryMemory function
author: windows-driver-content
description: The WdfRegistryQueryMemory method retrieves the data that is currently assigned to a specified registry value, stores the data in a framework-allocated buffer, and creates a framework memory object to represent the buffer.
old-location: wdf\wdfregistryquerymemory.htm
old-project: wdf
ms.assetid: 2d689ede-418e-4bf3-8c0e-82ded1085382
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfregistry/WdfRegistryQueryMemory, DFRegKeyObjectRef_97e02e2b-59d4-4041-a22d-e3a8905c096f.xml, wdf.wdfregistryquerymemory, WdfRegistryQueryMemory method, kmdf.wdfregistryquerymemory, WdfRegistryQueryMemory
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
-	WdfRegistryQueryMemory
product: Windows
targetos: Windows
req.typenames: "*PWDF_QUERY_INTERFACE_CONFIG, WDF_QUERY_INTERFACE_CONFIG"
req.product: Windows 10 or later.
---

# WdfRegistryQueryMemory function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryQueryMemory</b> method retrieves the data that is currently assigned to a specified registry value, stores the data in a framework-allocated buffer, and creates a framework memory object to represent the buffer.


## -syntax


````
NTSTATUS WdfRegistryQueryMemory(
  _In_      WDFKEY                 Key,
  _In_      PCUNICODE_STRING       ValueName,
  _In_      POOL_TYPE              PoolType,
  _In_opt_  PWDF_OBJECT_ATTRIBUTES MemoryAttributes,
  _Out_     WDFMEMORY              *Memory,
  _Out_opt_ PULONG                 ValueType
);
````


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a value name. 


### -param PoolType [in]

A <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>-typed value that specifies the type of memory to be allocated for the data buffer. 


### -param MemoryAttributes [in, optional]

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for the new memory object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES. 


### -param Memory [out]

A pointer to a location that receives a handle to the new memory object. 


### -param ValueType [out, optional]

A pointer to a location that receives the data type. For a list of data type values, see the <b>Type</b> member of <a href="..\wdm\ns-wdm-_key_value_basic_information.md">KEY_VALUE_BASIC_INFORMATION</a>. This pointer is optional and can be <b>NULL</b>.


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

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerymemory.md">WdfRegistryQueryMemory</a> was not called at IRQL = PASSIVE_LEVEL. 

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

For a list of other return values that the <b>WdfRegistryQueryMemory</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


When a driver calls <b>WdfRegistryQueryMemory</b>, the framework allocates a buffer that is large enough to hold the specified registry value's data. After <b>WdfRegistryQueryMemory</b> returns, the driver can call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a> to obtain a pointer to the buffer and the buffer's size.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.



## -see-also

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryvalue.md">WdfRegistryQueryValue</a>

<a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerystring.md">WdfRegistryQueryString</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerymultistring.md">WdfRegistryQueryMultiString</a>

<a href="..\wdm\ns-wdm-_key_value_basic_information.md">KEY_VALUE_BASIC_INFORMATION</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryulong.md">WdfRegistryQueryULong</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryunicodestring.md">WdfRegistryQueryUnicodeString</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryQueryMemory method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

