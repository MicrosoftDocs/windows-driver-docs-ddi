---
UID: NF:wdfmemory.WdfMemoryAssignBuffer
title: WdfMemoryAssignBuffer function (wdfmemory.h)
description: The WdfMemoryAssignBuffer method assigns a specified buffer to a memory object that a driver created by calling WdfMemoryCreatePreallocated.
old-location: wdf\wdfmemoryassignbuffer.htm
tech.root: wdf
ms.assetid: f57fe6ac-87ad-4db8-a715-816885b87d68
ms.date: 02/26/2018
keywords: ["WdfMemoryAssignBuffer function"]
ms.keywords: DFMemoryObjectRef_c2bf3437-5c1e-44d6-97ab-6ede16f7bc53.xml, WdfMemoryAssignBuffer, WdfMemoryAssignBuffer method, kmdf.wdfmemoryassignbuffer, wdf.wdfmemoryassignbuffer, wdfmemory/WdfMemoryAssignBuffer
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA, DriverCreate, MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctlA, MemAfterReqCompletedReadA, MemAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfMemoryAssignBuffer
 - wdfmemory/WdfMemoryAssignBuffer
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
 - WdfMemoryAssignBuffer
---

# WdfMemoryAssignBuffer function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfMemoryAssignBuffer</b> method assigns a specified buffer to a memory object that a driver created by calling <a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreatepreallocated">WdfMemoryCreatePreallocated</a>.

## -parameters

### -param Memory 

[in]
A handle to a framework memory object that was obtained by calling <a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreatepreallocated">WdfMemoryCreatePreallocated</a>.

### -param Buffer 

[in]
A pointer to a driver-supplied buffer.

### -param BufferSize 

[in]
The nonzero size, in bytes, of the buffer that <i>Buffer</i> points to.

## -returns

<b>WdfMemoryAssignBuffer</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
</table>
 

This method also might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

The method can assign a buffer to a memory object that <a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreatepreallocated">WdfMemoryCreatePreallocated</a> created, but not to a memory object that <a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a> created.

The buffer that the <i>Buffer</i> parameter points to can be allocated from the pageable or non-pageable memory pool. If the driver allocates the buffer from the pageable pool, or if the buffer is from pageable pool because it came from a user-mode application, the driver must access the buffer only at IRQL < DISPATCH_LEVEL. (Note that the driver's <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> and <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback functions, if provided, can be called at IRQL <= DISPATCH_LEVEL.)

For more information about framework memory objects, see <a href="/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.


#### Examples

The following code example allocates a buffer and then assigns the buffer to a framework memory object.

```cpp
PVOID  pNewBuffer = NULL;

pNewBuffer = ExAllocatePoolWithTag(
                                   NonPagedPool,
                                   NEW_BUFFER_SIZE,
                                   MY_DRIVER_TAG
                                   );
if (pNewBuffer == NULL){
    goto Error;
}

status = WdfMemoryAssignBuffer(
                               memHandle,
                               pNewBuffer,
                               NEW_BUFFER_SIZE
                               );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreatepreallocated">WdfMemoryCreatePreallocated</a>