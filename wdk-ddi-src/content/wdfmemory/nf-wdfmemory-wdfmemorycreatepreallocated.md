---
UID: NF:wdfmemory.WdfMemoryCreatePreallocated
title: WdfMemoryCreatePreallocated function (wdfmemory.h)
description: The WdfMemoryCreatePreallocated method creates a framework memory object for a driver-supplied memory buffer.
old-location: wdf\wdfmemorycreatepreallocated.htm
tech.root: wdf
ms.assetid: 8c4f9abc-f03d-4084-b0ce-34aea5dd7d96
ms.date: 02/26/2018
keywords: ["WdfMemoryCreatePreallocated function"]
ms.keywords: DFMemoryObjectRef_03f219cd-a77b-4a17-b67a-2b01e0aeb3e6.xml, WdfMemoryCreatePreallocated, WdfMemoryCreatePreallocated method, kmdf.wdfmemorycreatepreallocated, wdf.wdfmemorycreatepreallocated, wdfmemory/WdfMemoryCreatePreallocated
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfMemoryCreatePreallocated
 - wdfmemory/WdfMemoryCreatePreallocated
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
 - WdfMemoryCreatePreallocated
---

# WdfMemoryCreatePreallocated function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfMemoryCreatePreallocated</b> method creates a framework memory object for a driver-supplied memory buffer.

## -parameters

### -param Attributes 

[in, optional]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for the new memory object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param Buffer 

[in]
A pointer to a driver-supplied buffer.

### -param BufferSize 

[in]
The nonzero size, in bytes, of the buffer that <i>Buffer</i> points to.

### -param Memory 

[out]
A pointer to a location that receives a handle to the new memory object.

## -returns

<b>WdfMemoryCreatePreallocated</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfMemoryCreatePreallocated</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.



This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

The <b>WdfMemoryCreatePreallocated</b> method creates a framework memory object for a buffer that the driver has previously allocated or obtained. 

Your driver can call <b>WdfMemoryCreatePreallocated</b> if you need to create memory objects that represent pre-existing memory buffers. For example, the driver might receive a driver-defined structure within a buffer for an I/O request that contains an internal I/O control code. The driver can call <b>WdfMemoryCreatePreallocated</b> to create a memory object so that the driver can pass the structure to an I/O target. 

After a driver has called <b>WdfMemoryCreatePreallocated</b>, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemoryassignbuffer">WdfMemoryAssignBuffer</a> to assign a different buffer to the memory object that <b>WdfMemoryCreatePreallocated</b> created.

The default parent object for each memory object is the framework driver object that represents the driver that called <b>WdfMemoryCreatePreallocated</b>. If your driver creates a memory object that it uses with a specific device object, request object, or other framework object, it should set the memory object's parent appropriately. The memory object will be deleted when the parent object is deleted. If you do not change the default parent object, the memory object will remain in memory until the I/O manager unloads your driver.

A driver can also delete a memory object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a>.

When the framework memory object that <b>WdfMemoryCreatePreallocated</b> created is deleted, the framework does not deallocate the pre-existing buffer. Likewise, a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemoryassignbuffer">WdfMemoryAssignBuffer</a> does not deallocate the previously assigned buffer.

For more information about framework memory objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.


#### Examples

The following code example allocates a buffer and then creates a framework memory object for the buffer.

```cpp
PVOID  pBuffer = NULL;
WDF_OBJECT_ATTRIBUTES  attributes;
WDFMEMORY  memHandle;

pBuffer = ExAllocatePoolWithTag(
                                NonPagedPool,
                                MY_BUFFER_SIZE,
                                MY_DRIVER_TAG
                                );
if (pBuffer == NULL){
    goto Error;
}
WDF_OBJECT_ATTRIBUTES_INIT(&attributes);
attributes.ParentObject = requestHandle;

status = WdfMemoryCreatePreallocated(
                                     attributes,
                                     pBuffer,
                                     MY_BUFFER_SIZE,
                                     &memHandle
                                     );
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemoryassignbuffer">WdfMemoryAssignBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreatefromlookaside">WdfMemoryCreateFromLookaside</a>

