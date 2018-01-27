---
UID: NF:ntifs.FsRtlAllocatePoolWithTag
title: FsRtlAllocatePoolWithTag macro
author: windows-driver-content
description: The FsRtlAllocatePoolWithTag routine allocates pool memory.
old-location: ifsk\fsrtlallocatepoolwithtag.htm
old-project: ifsk
ms.assetid: a9ea59d1-1d51-4332-b497-7d2b7f39e686
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fsrtlallocatepoolwithtag, FsRtlAllocatePoolWithTag, fsrtlref_1137174c-fe54-4575-98a6-64a569f91b96.xml, ntifs/FsRtlAllocatePoolWithTag, FsRtlAllocatePoolWithTag routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL (see Remarks section)
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	FsRtlAllocatePoolWithTag
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlAllocatePoolWithTag macro


## -description


The <b>FsRtlAllocatePoolWithTag</b> routine allocates pool memory. 


## -syntax


````
PVOID FsRtlAllocatePoolWithTag(
  _In_ POOL_TYPE PoolType,
  _In_ ULONG     NumberOfBytes,
  _In_ ULONG     Tag
);
````


## -parameters




### -param PoolType [in]

Type of pool to allocate. One of the following:


<ul>
<li><b>NonPagedPool</b></li>
<li><b>PagedPool</b></li>
<li><b>NonPagedPoolCacheAligned</b></li>
<li><b>PagedPoolCacheAligned</b></li>
</ul>

<div class="alert"><b>Note</b>    The <b>NonPagedPoolMustSucceed</b> and <b>NonPagedPoolCacheAlignedMustS</b> pool types are obsolete and should no longer be used. </div><div> </div>

### -param NumberOfBytes [in]

Number of bytes to allocate. This parameter is required and cannot be zero. 


### -param Tag [in]

Specifies the pool tag for the allocated memory. Drivers normally specify the pool tag as a string of one to four 7-bit ASCII characters, delimited by single quotation marks (for example, 'abcd'). This parameter is required and cannot be zero. 


## -remarks


If a pool allocation failure occurs, <b>FsRtlAllocatePoolWithTag</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlAllocatePoolWithTag</b> in a <b>try-except</b> or <b>try-finally</b> statement.

The system associates the pool tag specified by the <i>Tag</i> parameter with the allocated buffer. Programming tools, such as the Windows Debugger (WinDbg), can display the pool tag associated with each allocated buffer. The value of the pool tag is normally displayed in reversed order. For example, if a caller passes 'Fred' as the value of the <i>Tag</i> parameter, this value would appear as 'derF' if pool is dumped or when tracking pool usage in the debugger. 

For more information about memory management, see <a href="https://msdn.microsoft.com/e030a37c-26ab-4177-9980-4336928975e1">Memory Management</a>. 

Callers of <b>FsRtlAllocatePoolWithTag</b> must be running at IRQL &lt;= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must specify a <b>NonPaged</b><i>XxxPoolType</i>. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.



## -see-also

<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>

<a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlAllocatePoolWithTag routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

