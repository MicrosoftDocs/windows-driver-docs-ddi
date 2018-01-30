---
UID: NF:wdm.RtlFindClearBits
title: RtlFindClearBits function
author: windows-driver-content
description: The RtlFindClearBits routine searches for a range of clear bits of a requested size within a bitmap.
old-location: kernel\rtlfindclearbits.htm
old-project: kernel
ms.assetid: 5279d126-8fd3-43dd-be03-2134e46a3ef9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlFindClearBits, wdm/RtlFindClearBits, k109_bf520772-12d8-403e-8b57-31a24e9a27b6.xml, kernel.rtlfindclearbits, RtlFindClearBits routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<= APC_LEVEL (See Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlFindClearBits
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlFindClearBits function


## -description


The <b>RtlFindClearBits</b> routine searches for a range of clear bits of a requested size within a bitmap. 


## -syntax


````
ULONG RtlFindClearBits(
  _In_ PRTL_BITMAP BitMapHeader,
  _In_ ULONG       NumberToFind,
  _In_ ULONG       HintIndex
);
````


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine. 


### -param NumberToFind [in]

Specifies how many contiguous clear bits will satisfy this request. 


### -param HintIndex [in]

Specifies a zero-based bit position from which to start looking for a clear bit range of the given size. 


## -returns


<b>RtlFindClearBits</b> either returns the zero-based starting bit index for a clear bit range of at least the requested size, or it returns 0xFFFFFFFF if it cannot find such a range within the given bitmap. 



## -remarks


For a successful call, the returned bit position is not necessarily equivalent to the given <i>HintIndex</i>. If necessary, <b>RtlFindClearBits</b> searches the whole bitmap to locate a clear bit range of the requested size. However, it starts searching for the requested range from <i>HintIndex</i>, so callers can find such a range more quickly when they can supply appropriate hints about where to start looking. 

Callers of <b>RtlFindClearBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindClearBits</b> can be called at any IRQL.



## -see-also

<a href="..\wdm\nf-wdm-rtlfindclearbitsandset.md">RtlFindClearBitsAndSet</a>

<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>

<a href="..\wdm\nf-wdm-rtlfindsetbits.md">RtlFindSetBits</a>

<a href="..\wdm\nf-wdm-rtlfindfirstrunclear.md">RtlFindFirstRunClear</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>

<a href="..\wdm\nf-wdm-rtlfindlongestrunclear.md">RtlFindLongestRunClear</a>

<a href="..\wdm\nf-wdm-rtlarebitsclear.md">RtlAreBitsClear</a>

<a href="..\wdm\nf-wdm-rtlnumberofclearbits.md">RtlNumberOfClearBits</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlFindClearBits routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

