---
UID: NF:wdfmemory.WdfMemoryCopyToBuffer
title: WdfMemoryCopyToBuffer function
author: windows-driver-content
description: The WdfMemoryCopyToBuffer method copies the contents of a specified memory object's buffer into a specified destination buffer.
old-location: wdf\wdfmemorycopytobuffer.htm
old-project: wdf
ms.assetid: cb1fc590-3d3a-4b06-b467-28c3adb43706
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfmemory/WdfMemoryCopyToBuffer, PFN_WDFMEMORYCOPYTOBUFFER, DFMemoryObjectRef_8668c3aa-f5f0-4a1a-9290-27cf78fbcd24.xml, WdfMemoryCopyToBuffer method, wdf.wdfmemorycopytobuffer, WdfMemoryCopyToBuffer, kmdf.wdfmemorycopytobuffer
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
-	WdfMemoryCopyToBuffer
product: Windows
targetos: Windows
req.typenames: WDF_MEMORY_DESCRIPTOR_TYPE
req.product: Windows 10 or later.
---

# WdfMemoryCopyToBuffer function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfMemoryCopyToBuffer</b> method copies the contents of a specified memory object's buffer into a specified destination buffer.


## -syntax


````
NTSTATUS WdfMemoryCopyToBuffer(
  _In_  WDFMEMORY SourceMemory,
  _In_  size_t    SourceOffset,
  _Out_ PVOID     Buffer,
  _In_  size_t    NumBytesToCopyTo
);
````


## -parameters




### -param SourceMemory [in]

A handle to a framework memory object that represents the source buffer.


### -param SourceOffset [in]

An offset, in bytes, from the beginning of the source buffer. The copy operation begins at the specified offset in the source buffer.


### -param Buffer [out]

A pointer to a destination buffer.


### -param NumBytesToCopyTo [in]

The number of bytes to copy from the source buffer to the destination buffer. This value must not be greater than the size of the source buffer.


## -returns


<b>WdfMemoryCopyToBuffer</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
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
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The byte offset that the <i>SourceOffset</i> parameter specified was too large, or the <i>NumBytesToCopyTo</i> parameter was greater than the size of the source buffer.

</td>
</tr>
</table> 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


The framework does not allow the driver to copy more bytes than the source buffer that the <i>SourceMemory</i> parameter specifies can contain. 

For more information about framework memory objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.

If the source or destination buffer was allocated from the pageable memory pool, the <b>WdfMemoryCopyToBuffer</b> method must be called at IRQL &lt;= APC_LEVEL. Otherwise, the method can be called at any IRQL.



## -see-also

<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycopyfrombuffer.md">WdfMemoryCopyFromBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfMemoryCopyToBuffer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

