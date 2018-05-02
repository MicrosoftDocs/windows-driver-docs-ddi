---
UID: NF:wdm.RtlZeroMemory
title: RtlZeroMemory macro
author: windows-driver-content
description: The RtlZeroMemory routine fills a block of memory with zeros, given a pointer to the block and the length, in bytes, to be filled.
old-location: kernel\rtlzeromemory.htm
old-project: kernel
ms.assetid: e9e20d9c-0f2f-4ab1-a249-3e09bb6a7a22
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlZeroMemory, RtlZeroMemory routine [Kernel-Mode Driver Architecture], k109_63d9f0fb-d698-4707-9018-de2fa851a94b.xml, kernel.rtlzeromemory, wdm/RtlZeroMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Smclib.h, Minitape.h, Scsi.h, Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlZeroMemory
product: Windows
targetos: Windows
req.typenames: 
---

# RtlZeroMemory macro


## -description


The <b>RtlZeroMemory</b> routine fills a block of memory with zeros, given a pointer to the block and the length, in bytes, to be filled.


## -parameters




### -param Destination [out]

A pointer to the memory block to be filled with zeros.


### -param Length [in]

The number of bytes to fill with zeros.


## -remarks



To zero out a memory buffer to erase security-sensitive data, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff562768">RtlSecureZeroMemory</a> instead.

Callers of <b>RtlZeroMemory</b> can be running at any IRQL if the destination memory block is in nonpaged system memory. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561870">RtlFillMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562768">RtlSecureZeroMemory</a>
 

 

