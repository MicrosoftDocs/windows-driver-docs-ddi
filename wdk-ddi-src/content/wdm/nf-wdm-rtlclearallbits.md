---
UID: NF:wdm.RtlClearAllBits
title: RtlClearAllBits function
author: windows-driver-content
description: The RtlClearAllBits routine sets all bits in a given bitmap variable to zero.
old-location: kernel\rtlclearallbits.htm
old-project: kernel
ms.assetid: 8271b13a-a64e-4d5e-b319-283255b8127f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.rtlclearallbits, wdm/RtlClearAllBits, RtlClearAllBits routine [Kernel-Mode Driver Architecture], RtlClearAllBits, k109_6fb17a55-6839-411c-9289-720657ba4983.xml
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: "<= APC_LEVEL (See Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlClearAllBits
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlClearAllBits function


## -description


The <b>RtlClearAllBits</b> routine sets all bits in a given bitmap variable to zero. 


## -syntax


````
VOID RtlClearAllBits(
  _In_ PRTL_BITMAP BitMapHeader
);
````


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine. 


## -returns



None




## -remarks



Callers of <b>RtlClearAllBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlClearAllBits</b> can be called at any IRQL.




## -see-also

<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>



<a href="..\wdm\nf-wdm-rtlclearbits.md">RtlClearBits</a>



<a href="..\wdm\nf-wdm-rtlfindsetbits.md">RtlFindSetBits</a>



<a href="..\wdm\nf-wdm-rtlarebitsclear.md">RtlAreBitsClear</a>



<a href="..\wdm\nf-wdm-rtlnumberofsetbits.md">RtlNumberOfSetBits</a>



<a href="..\wdm\nf-wdm-rtlfindsetbitsandclear.md">RtlFindSetBitsAndClear</a>



<a href="..\wdm\nf-wdm-rtlarebitsset.md">RtlAreBitsSet</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlClearAllBits routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

