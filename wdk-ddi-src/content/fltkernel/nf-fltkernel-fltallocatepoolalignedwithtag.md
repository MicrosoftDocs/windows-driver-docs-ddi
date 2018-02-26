---
UID: NF:fltkernel.FltAllocatePoolAlignedWithTag
title: FltAllocatePoolAlignedWithTag function
author: windows-driver-content
description: FltAllocatePoolAlignedWithTag allocates a device-aligned buffer for use in a noncached I/O operation.
old-location: ifsk\fltallocatepoolalignedwithtag.htm
old-project: ifsk
ms.assetid: ffb1493f-6076-4b93-8431-b3ffd4679f96
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, F, FltAllocatePoolAlignedWithTag, FltAllocatePoolAlignedWithTag function [Installable File System Drivers], FltApiRef_a_to_d_b617aed0-5103-4a1e-aa0d-86247d99e803.xml, P, T, W, a, c, d, e, fltkernel/FltAllocatePoolAlignedWithTag, g, h, i, ifsk.fltallocatepoolalignedwithtag, l, n, o, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltAllocatePoolAlignedWithTag
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltAllocatePoolAlignedWithTag function


## -description


<b>FltAllocatePoolAlignedWithTag</b> allocates a device-aligned buffer for use in a noncached I/O operation. 


## -syntax


````
PVOID FltAllocatePoolAlignedWithTag(
  _In_ PFLT_INSTANCE Instance,
  _In_ POOL_TYPE     PoolType,
  _In_ SIZE_T        NumberOfBytes,
  _In_ ULONG         Tag
);
````


## -parameters




### -param Instance [in]

Opaque instance pointer for a caller-owned minifilter driver instance that is attached to the volume. This parameter is required and cannot be <b>NULL</b>. 


### -param PoolType [in]

Type of pool to allocate. One of the following: 

<b>NonPagedPool</b>

<b>PagedPool</b>

<b>NonPagedPoolCacheAligned</b>

<b>PagedPoolCacheAligned</b>

See <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a> for a description of the available pool memory types. 


### -param NumberOfBytes [in]

Number of bytes to allocate. This parameter is required and can be zero. 


### -param Tag [in]

Specifies the pool tag for the allocated memory. Drivers normally specify the pool tag as a string of one to four 7-bit ASCII characters, delimited by single quotation marks (for example, 'abcd'). This parameter is required and cannot be zero. 


## -returns



If not enough free pool is available to satisfy the request, <b>FltAllocatePoolAlignedWithTag</b> returns a <b>NULL</b> pointer. Otherwise, <b>FltAllocatePoolAlignedWithTag</b> returns a pointer to the newly allocated buffer. 




## -remarks



<b>FltAllocatePoolAlignedWithTag</b> allocates a buffer that is aligned in accordance with the underlying device for the given volume. Such device-aligned buffers are required for noncached I/O. (They can also be used for cached I/O.) Thus when calling routines that perform noncached I/O, such as <a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a> and <a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>, minifilter drivers should call <b>FltAllocatePoolAlignedWithTag</b> instead of <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>. 

If the caller specifies a value of zero for the <i>NumberOfBytes</i> parameter, <b>FltAllocatePoolAlignedWithTag</b> allocates the smallest amount of memory that meets the alignment requirement. 

The system associates the pool tag specified by the <i>Tag</i> parameter with the allocated buffer. Programming tools, such as the Windows Debugger (WinDbg), can display the pool tag associated with each allocated buffer. The value of the pool tag is normally displayed in reversed order. For example, if a caller passes 'Fred' as the value of the <i>Tag</i> parameter, this value would appear as 'derF' if pool is dumped or when tracking pool usage in the debugger. 

For more information about memory management, see <a href="https://msdn.microsoft.com/e030a37c-26ab-4177-9980-4336928975e1">Memory Management</a>. 

When the buffer that <b>FltAllocatePoolAlignedWithTag</b> allocates is no longer needed, the caller is responsible for freeing it by calling <a href="..\fltkernel\nf-fltkernel-fltfreepoolalignedwithtag.md">FltFreePoolAlignedWithTag</a>. 

Callers of <b>FltAllocatePoolAlignedWithTag</b> can be running at IRQL DISPATCH_LEVEL only if a NonPaged<i>XxxPoolType</i> is specified. Otherwise, callers must be running at IRQL &lt;= APC_LEVEL. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltfreepoolalignedwithtag.md">FltFreePoolAlignedWithTag</a>



<a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>



<a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>



<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAllocatePoolAlignedWithTag function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

