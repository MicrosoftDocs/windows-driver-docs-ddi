---
UID: NF:wdfmemory.WdfMemoryAssignBuffer
title: WdfMemoryAssignBuffer function
author: windows-driver-content
description: The WdfMemoryAssignBuffer method assigns a specified buffer to a memory object that a driver created by calling WdfMemoryCreatePreallocated.
old-location: wdf\wdfmemoryassignbuffer.htm
old-project: wdf
ms.assetid: f57fe6ac-87ad-4db8-a715-816885b87d68
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfMemoryAssignBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfMemoryAssignBuffer
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
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
req.typenames: WDF_MEMORY_DESCRIPTOR_TYPE
req.product: Windows 10 or later.
---

# WdfMemoryAssignBuffer function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfMemoryAssignBuffer</b> method assigns a specified buffer to a memory object that a driver created by calling <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a>.



## -syntax

````
NTSTATUS WdfMemoryAssignBuffer(
  _In_ WDFMEMORY Memory,
  _In_ PVOID     Buffer,
  _In_ size_t    BufferSize
);
````


## -parameters

### -param Memory [in]

A handle to a framework memory object that was obtained by calling <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a>.


### -param Buffer [in]

A pointer to a driver-supplied buffer.


### -param BufferSize [in]

The nonzero size, in bytes, of the buffer that <i>Buffer</i> points to.


## -returns
<b>WdfMemoryAssignBuffer</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
The method can assign a buffer to a memory object that <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a> created, but not to a memory object that <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a> created.

The buffer that the <i>Buffer</i> parameter points to can be allocated from the pageable or non-pageable memory pool. If the driver allocates the buffer from the pageable pool, or if the buffer is from pageable pool because it came from a user-mode application, the driver must access the buffer only at IRQL &lt; DISPATCH_LEVEL. (Note that the driver's <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> and <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback functions, if provided, can be called at IRQL &lt;= DISPATCH_LEVEL.)

For more information about framework memory objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.

The following code example allocates a buffer and then assigns the buffer to a framework memory object.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>
</dt>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfMemoryAssignBuffer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

