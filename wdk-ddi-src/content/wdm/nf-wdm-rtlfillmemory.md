---
UID: NF:wdm.RtlFillMemory
title: RtlFillMemory macro
author: windows-driver-content
description: The RtlFillMemory routine fills a block of memory with the specified fill value.
old-location: kernel\rtlfillmemory.htm
old-project: kernel
ms.assetid: 9a73331a-cc73-4a47-948b-a821600ca6a6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wdm/RtlFillMemory, RtlFillMemory routine [Kernel-Mode Driver Architecture], kernel.rtlfillmemory, k109_db7a2a9f-c7b5-40c3-9755-e386bbaf5353.xml, RtlFillMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.lib: NtDll.lib (user mode); NtosKrnl.lib (kernel mode)
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: Any level (See Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtDll.dll
-	NtosKrnl.exe
-	API-MS-Win-Core-rtlsupport-l1-1-0.dll
apiname:
-	RtlFillMemory
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlFillMemory macro


## -description


The <b>RtlFillMemory</b> routine fills a block of memory with the specified fill value.


## -syntax


````
VOID RtlFillMemory(
  _Out_ VOID UNALIGNED *Destination,
  _In_  SIZE_T         Length,
  _In_  UCHAR          Fill
);
````


## -parameters




### -param Destination [out]

A pointer to the block of memory to be filled.


### -param Length [in]

The number of bytes in the block of memory to be filled.


### -param Fill [in]

The value to fill the destination memory block with. This value is copied to every byte in the memory block that is defined by <i>Destination</i> and <i>Length</i>.


## -remarks



Callers of <b>RtlFillMemory</b> can be running at any IRQL if the destination memory block is in nonpaged system memory. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.




## -see-also

<a href="..\minitape\nf-minitape-rtlzeromemory.md">RtlZeroMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlFillMemory routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

