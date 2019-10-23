---
UID: NF:wdfmemory.WdfMemoryCopyFromBuffer
title: WdfMemoryCopyFromBuffer function (wdfmemory.h)
description: The WdfMemoryCopyFromBuffer method copies the contents of a specified source buffer into a specified memory object's buffer.
old-location: wdf\wdfmemorycopyfrombuffer.htm
tech.root: wdf
ms.assetid: 702d5239-48cd-4c11-90bc-a86ab27b8cfe
ms.date: 02/26/2018
ms.keywords: DFMemoryObjectRef_5e7dd10c-6902-4965-b868-8f3ba25d4fbc.xml, WdfMemoryCopyFromBuffer, WdfMemoryCopyFromBuffer method, kmdf.wdfmemorycopyfrombuffer, wdf.wdfmemorycopyfrombuffer, wdfmemory/WdfMemoryCopyFromBuffer
ms.topic: function
f1_keywords:
 - "wdfmemory/WdfMemoryCopyFromBuffer"
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
req.irql: Any level (see Remarks section)
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
- WdfMemoryCopyFromBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfMemoryCopyFromBuffer function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfMemoryCopyFromBuffer</b> method copies the contents of a specified source buffer into a specified memory object's buffer.


## -parameters




### -param DestinationMemory [in]

A handle to a framework memory object that represents the destination buffer.


### -param DestinationOffset [in]

An offset, in bytes, from the beginning of the destination buffer. The copy operation begins at the specified offset in the destination buffer.


### -param Buffer [in]

A pointer to a source buffer.


### -param NumBytesToCopyFrom [in]

The number of bytes to copy from the source buffer to the destination buffer. This value must not be greater than the size of the source buffer.


## -returns



<b>WdfMemoryCopyFromBuffer</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
<dt><b>STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>
</td>
<td width="60%">
The byte offset that the <i>DestinationOffset</i> parameter specified was too large.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The size of the destination buffer that the <i>DestinationOffset</i> parameter specified, starting at the destination offset, was greater than the <i>NumBytesToCopyFrom</i> parameter.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The framework verifies that the destination buffer is large enough to receive the amount of data that the <i>NumBytesToCopyFrom</i> parameter specifies.

For more information about framework memory objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.

If the source or destination buffer was allocated from the pageable memory pool, the <b>WdfMemoryCopyFromBuffer</b> method must be called at IRQL <= APC_LEVEL. Otherwise, the method can be called at any IRQL.


#### Examples

The following code example obtains a handle to the framework memory object that represents an I/O request's output buffer, and then it copies the contents of another buffer into the I/O request's output buffer.

```cpp
WDFMEMORY  memoryBuffer;
NTSTATUS  status;

status = WdfRequestRetrieveOutputMemory(
                                        Request,
                                        &memoryBuffer
                                        );
if (!NT_SUCCESS(status)) {
    goto Error;
}
status = WdfMemoryCopyFromBuffer(
                                 memoryBuffer,
                                 0,
                                 deviceContext->Buffer,
                                 Length
                                 );
if (!NT_SUCCESS(status)) {
    goto Error;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycopytobuffer">WdfMemoryCopyToBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a>
 

 

