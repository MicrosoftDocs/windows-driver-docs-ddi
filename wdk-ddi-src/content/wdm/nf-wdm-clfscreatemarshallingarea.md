---
UID: NF:wdm.ClfsCreateMarshallingArea
title: ClfsCreateMarshallingArea function
author: windows-driver-content
description: The ClfsCreateMarshallingArea routine creates a marshalling area for a CLFS stream and returns a pointer to an opaque context that represents the new marshalling area.
old-location: kernel\clfscreatemarshallingarea.htm
old-project: kernel
ms.assetid: c841d8fb-fa42-4ce5-aedb-c7c13bcc2ba7
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ClfsCreateMarshallingArea, ClfsCreateMarshallingArea routine [Kernel-Mode Driver Architecture], Clfs_7b5e3208-8dfb-4fbf-b2a9-77ecc5765df6.xml, kernel.clfscreatemarshallingarea, wdm/ClfsCreateMarshallingArea
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsCreateMarshallingArea
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsCreateMarshallingArea function


## -description


The <b>ClfsCreateMarshallingArea</b> routine creates a marshalling area for a CLFS stream and returns a pointer to an opaque context that represents the new marshalling area.


## -syntax


````
NTSTATUS ClfsCreateMarshallingArea(
  _In_     PLOG_FILE_OBJECT   plfoLog,
  _In_     POOL_TYPE          ePoolType,
  _In_opt_ PALLOCATE_FUNCTION pfnAllocBuffer,
  _In_opt_ PFREE_FUNCTION     pfnFreeBuffer,
  _In_     ULONG              cbMarshallingBuffer,
  _In_     ULONG              cMaxWriteBuffers,
  _In_     ULONG              cMaxReadBuffers,
  _Out_    PVOID              *ppvMarshalContext
);
````


## -parameters




### -param plfoLog [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents a CLFS stream. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>.


### -param ePoolType [in]

A <a href="..\wudfwdm\ne-wudfwdm-_pool_type.md">POOL_TYPE</a> value that specifies the type of memory (paged, non-paged, for example) that the new marshalling area will use for its log I/O blocks.


### -param pfnAllocBuffer [in, optional]

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


### -param pfnFreeBuffer [in, optional]

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

### -param cbMarshallingBuffer [in]

The size, in bytes, of the individual log I/O blocks that the new marshalling area uses. This must be a multiple of the sector size on the stable storage medium. The sector size is the <i>lpBytesPerSector</i> value returned from <b>GetDiskFreeSpace</b>.


### -param cMaxWriteBuffers [in]

The maximum number of I/O blocks that can be allocated at one time for write operations. This parameter affects the frequency of data flushes. If you do not need to control the frequency of data flushes, set this parameter to INFINITE.


### -param cMaxReadBuffers [in]

The maximum number of log I/O blocks that can be allocated at one time for read operations.


### -param ppvMarshalContext [out]

A pointer to a variable that receives a pointer to an opaque context that represents the new marshalling area.


## -returns



<b>ClfsCreateMarshallingArea</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



The <i>pfnAllocBuffer</i> and <i>pfnFreeBuffer</i> parameters must both point to caller-allocated functions, or they must both be <b>NULL</b>. If they are both <b>NULL</b>, CLFS provides default functions for allocating and freeing log I/O blocks.

Before calling <b>ClfsCreateMarshallingArea</b>, you must add at least two containers to the underlying log by calling <a href="..\wdm\nf-wdm-clfsaddlogcontainer.md">ClfsAddLogContainer</a> or <a href="..\wdm\nf-wdm-clfsaddlogcontainerset.md">ClfsAddLogContainerSet</a>.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a>



<a href="..\wdm\nf-wdm-clfsdeletemarshallingarea.md">ClfsDeleteMarshallingArea</a>



<a href="..\wudfwdm\ne-wudfwdm-_pool_type.md">POOL_TYPE</a>



<a href="..\wdm\nf-wdm-clfsaddlogcontainer.md">ClfsAddLogContainer</a>



<a href="..\wdm\nf-wdm-clfsaddlogcontainerset.md">ClfsAddLogContainerSet</a>



<a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsCreateMarshallingArea routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

