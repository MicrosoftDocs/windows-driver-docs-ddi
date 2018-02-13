---
UID: NF:wdm.RtlClearBit
title: RtlClearBit function
author: windows-driver-content
description: The RtlClearBit routine sets the specified bit in a bitmap to zero.
old-location: kernel\rtlclearbit.htm
old-project: kernel
ms.assetid: bfc75a17-a0de-436e-aebf-902fd841871a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k109_f785121e-f076-4f31-90ab-4bec446e3cc9.xml, wdm/RtlClearBit, RtlClearBit routine [Kernel-Mode Driver Architecture], kernel.rtlclearbit, RtlClearBit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
-	RtlClearBit
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlClearBit function


## -description


The <b>RtlClearBit</b> routine sets the specified bit in a bitmap to zero. 


## -syntax


````
VOID RtlClearBit(
  _In_ PRTL_BITMAP BitMapHeader,
  _In_ ULONG       BitNumber
);
````


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine. 


### -param BitNumber [in]

Specifies the zero-based index of the bit within the bitmap. The routine sets this bit to zero. 


## -returns



None




## -remarks



Callers of <b>RtlClearBit</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlClearBit</b> can be called at any IRQL.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlClearBit routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

