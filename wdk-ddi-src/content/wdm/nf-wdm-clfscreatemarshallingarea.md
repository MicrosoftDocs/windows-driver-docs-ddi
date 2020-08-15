---
UID: NF:wdm.ClfsCreateMarshallingArea
title: ClfsCreateMarshallingArea function (wdm.h)
description: The ClfsCreateMarshallingArea routine creates a marshalling area for a CLFS stream and returns a pointer to an opaque context that represents the new marshalling area.
old-location: kernel\clfscreatemarshallingarea.htm
tech.root: kernel
ms.assetid: c841d8fb-fa42-4ce5-aedb-c7c13bcc2ba7
ms.date: 04/30/2018
keywords: ["ClfsCreateMarshallingArea function"]
ms.keywords: ClfsCreateMarshallingArea, ClfsCreateMarshallingArea routine [Kernel-Mode Driver Architecture], Clfs_7b5e3208-8dfb-4fbf-b2a9-77ecc5765df6.xml, kernel.clfscreatemarshallingarea, wdm/ClfsCreateMarshallingArea
f1_keywords:
 - "wdm/ClfsCreateMarshallingArea"
 - "ClfsCreateMarshallingArea"
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Clfs.sys
- Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
- ClfsCreateMarshallingArea
targetos: Windows
req.typenames: 
---

# ClfsCreateMarshallingArea function


## -description


The <b>ClfsCreateMarshallingArea</b> routine creates a marshalling area for a CLFS stream and returns a pointer to an opaque context that represents the new marshalling area.


## -parameters




### -param plfoLog 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents a CLFS stream. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>.


### -param ePoolType 
[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a> value that specifies the type of memory (paged, non-paged, for example) that the new marshalling area will use for its log I/O blocks.


### -param pfnAllocBuffer 
[in, optional]
Either <b>NULL</b> or a pointer to a caller-supplied function that allocates a log I/O block for the marshalling area. The allocation function has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PVOID
(*PALLOCATE_FUNCTION) (
    IN POOL_TYPE PoolType,
    IN SIZE_T NumberOfBytes,
    IN ULONG Tag
    );</pre>
</td>
</tr>
</table></span></div>
The return value of the allocation function is a pointer to the newly allocated log I/O block.


### -param pfnFreeBuffer 
[in, optional]
Either <b>NULL</b> or a pointer to a caller-supplied function that frees a log I/O block that was previously allocated by <i>pfnAllocBuffer</i>. The function has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
(*PFREE_FUNCTION) (
    IN PVOID Buffer
    );</pre>
</td>
</tr>
</table></span></div>

### -param cbMarshallingBuffer 
[in]
The size, in bytes, of the individual log I/O blocks that the new marshalling area uses. This must be a multiple of the sector size on the stable storage medium. The sector size is the <i>lpBytesPerSector</i> value returned from <b>GetDiskFreeSpace</b>.


### -param cMaxWriteBuffers 
[in]
The maximum number of I/O blocks that can be allocated at one time for write operations. This parameter affects the frequency of data flushes. If you do not need to control the frequency of data flushes, set this parameter to INFINITE.


### -param cMaxReadBuffers 
[in]
The maximum number of log I/O blocks that can be allocated at one time for read operations.


### -param ppvMarshalContext 
[out]
A pointer to a variable that receives a pointer to an opaque context that represents the new marshalling area.


## -returns



<b>ClfsCreateMarshallingArea</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



The <i>pfnAllocBuffer</i> and <i>pfnFreeBuffer</i> parameters must both point to caller-allocated functions, or they must both be <b>NULL</b>. If they are both <b>NULL</b>, CLFS provides default functions for allocating and freeing log I/O blocks.

Before calling <b>ClfsCreateMarshallingArea</b>, you must add at least two containers to the underlying log by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainer">ClfsAddLogContainer</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainerset">ClfsAddLogContainerSet</a>.

For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainer">ClfsAddLogContainer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainerset">ClfsAddLogContainerSet</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsdeletemarshallingarea">ClfsDeleteMarshallingArea</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>
 

 

