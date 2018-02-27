---
UID: NF:video.VideoPortAllocatePool
title: VideoPortAllocatePool function
author: windows-driver-content
description: The VideoPortAllocatePool function allocates a block of pool memory, inserting a caller-supplied tag at the beginning of the memory.
old-location: display\videoportallocatepool.htm
old-project: display
ms.assetid: c981e56f-e582-4c06-8d32-b070d58065d2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: VideoPortAllocatePool, VideoPortAllocatePool function [Display Devices], VideoPort_Functions_a9163e5b-6519-4427-a748-066ad120022a.xml, display.videoportallocatepool, video/VideoPortAllocatePool
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortAllocatePool
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortAllocatePool function


## -description


The <b>VideoPortAllocatePool</b> function allocates a block of pool memory, inserting a caller-supplied tag at the beginning of the memory.


## -syntax


````
PVOID VideoPortAllocatePool(
  _In_ PVOID        HwDeviceExtension,
  _In_ VP_POOL_TYPE PoolType,
  _In_ SIZE_T       NumberOfBytes,
  _In_ ULONG        Tag
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param PoolType [in]

Specifies the type of memory pool to allocate. This parameter can be set to one of the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>VpNonPagedPool</b>

</td>
<td>
The pool is from nonpaged memory.

</td>
</tr>
<tr>
<td>
<b>VpPagedPool</b>

</td>
<td>
The pool is from paged memory.

</td>
</tr>
<tr>
<td>
<b>VpNonPagedPoolCacheAligned</b>

</td>
<td>
The pool is from cache-aligned, nonpaged memory.

</td>
</tr>
<tr>
<td>
<b>VpPagedPoolCacheAligned</b>

</td>
<td>
The pool is from cache-aligned, paged memory.

</td>
</tr>
</table>
 


### -param NumberOfBytes [in]

Specifies the number of bytes of memory to allocate.


### -param Tag [in]

Specifies a four-byte allocation tag, consisting of up to four ASCII characters, that uniquely identifies the driver that is allocating the memory. The tag string is delimited with single quotes.


## -returns



On successful allocation of the memory pool, <b>VideoPortAllocatePool</b> returns the address of the allocated memory pool. Otherwise, this function returns <b>NULL</b>.




## -remarks



<b>VideoPortAllocatePool</b> is intended to replace <b>VideoPortAllocateBuffer</b>, which is obsolete.

The <i>Tag</i> string should be specified in byte-reversed order. It is recommended that the first letter in the string (before it is reversed) be 'D' to denote a display driver; the other three bytes should be indicative of the driver name. For example, the <i>Tag</i> string 'zyxD' appears as 'Dxyz' if pool is dumped. The tag appears in any crash dump of the system that occurs.

Callers of <b>VideoPortAllocatePool</b> can be running at IRQL = DISPATCH_LEVEL only if the requested <i>PoolType</i> is one of the <b>VpNonPaged</b><i>Xxx</i> types. Otherwise, callers must be running at IRQL &lt; DISPATCH_LEVEL.




## -see-also

<a href="..\video\nf-video-videoportfreepool.md">VideoPortFreePool</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortAllocatePool function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

