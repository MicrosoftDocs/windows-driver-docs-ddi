---
UID: NF:wdm.RtlNumberOfSetBits
title: RtlNumberOfSetBits function
author: windows-driver-content
description: The RtlNumberOfSetBits routine returns a count of the set bits in a given bitmap variable.
old-location: kernel\rtlnumberofsetbits.htm
old-project: kernel
ms.assetid: 6208f750-4871-43b9-b848-011180d39fd8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: k109_b8b2c3f8-3ec3-4690-90bb-e5b120b5b062.xml, wdm/RtlNumberOfSetBits, RtlNumberOfSetBits, kernel.rtlnumberofsetbits, RtlNumberOfSetBits routine [Kernel-Mode Driver Architecture]
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
-	RtlNumberOfSetBits
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlNumberOfSetBits function


## -description


The <b>RtlNumberOfSetBits</b> routine returns a count of the set bits in a given bitmap variable. 


## -syntax


````
ULONG RtlNumberOfSetBits(
  _In_ PRTL_BITMAP BitMapHeader
);
````


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine. 


## -returns



<b>RtlNumberOfSetBits</b> returns a count of the bits that are currently set. 




## -remarks



Callers of <b>RtlNumberOfSetBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlNumberOfSetBits</b> can be called at any IRQL.




## -see-also

<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="..\wdm\nf-wdm-rtlfindsetbits.md">RtlFindSetBits</a>



<a href="..\wdm\nf-wdm-rtlnumberofclearbits.md">RtlNumberOfClearBits</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlNumberOfSetBits routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

