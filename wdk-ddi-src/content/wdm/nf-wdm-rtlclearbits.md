---
UID: NF:wdm.RtlClearBits
title: RtlClearBits function
author: windows-driver-content
description: The RtlClearBits routine sets all bits in the specified range of bits in the bitmap to zero.
old-location: kernel\rtlclearbits.htm
old-project: kernel
ms.assetid: 2c332700-7778-4342-b99b-093142496624
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlClearBits, RtlClearBits routine [Kernel-Mode Driver Architecture], k109_ee20da99-4d30-46dc-99c1-d3d8dfa92d08.xml, kernel.rtlclearbits, wdm/RtlClearBits
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
req.irql: "<= APC_LEVEL (See Remarks section.)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlClearBits
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlClearBits function


## -description


The <b>RtlClearBits</b> routine sets all bits in the specified range of bits in the bitmap to zero.


## -syntax


````
VOID RtlClearBits(
  _In_ PRTL_BITMAP BitMapHeader,
  _In_ ULONG       StartingIndex,
  _In_ ULONG       NumberToClear
);
````


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine.


### -param StartingIndex [in]

The index of the first bit in the bit range that is to be cleared. If the bitmap contains N bits, the bits are numbered from 0 to N-1.


### -param NumberToClear [in]

Specifies how many bits to clear. If the bitmap contains N bits, this parameter can be a value in the range 1 to (N - <i>StartingIndex</i>).


## -returns



This routine does not return a value.




## -remarks



If the <i>NumberToClear</i> parameter is zero, <b>RtlClearBits</b> simply returns control without clearing any bits.

The sum (<i>StartingIndex</i> + <i>NumberToClear</i>) must not exceed the <i>SizeOfBitMap</i> parameter value specified in the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> call that initialized the bitmap.

Callers of <b>RtlClearBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlClearBits</b> can be called at any IRQL.




## -see-also

<a href="..\wdm\nf-wdm-rtlfindsetbits.md">RtlFindSetBits</a>



<a href="..\wdm\nf-wdm-rtlnumberofsetbits.md">RtlNumberOfSetBits</a>



<a href="..\wdm\nf-wdm-rtlarebitsset.md">RtlAreBitsSet</a>



<a href="..\wdm\nf-wdm-rtlclearallbits.md">RtlClearAllBits</a>



<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="..\wdm\nf-wdm-rtlfindsetbitsandclear.md">RtlFindSetBitsAndClear</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlClearBits routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

