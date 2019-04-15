---
UID: NF:smclib.RtlZeroMemory
title: RtlZeroMemory macro (smclib.h)
description: The RtlZeroMemory routine fills a block of memory with zeros, given a pointer to the block and the length, in bytes, to be filled.
old-location: kernel\rtlzeromemory.htm
tech.root: kernel
ms.assetid: e9e20d9c-0f2f-4ab1-a249-3e09bb6a7a22
ms.date: 02/24/2018
ms.keywords: RtlZeroMemory, RtlZeroMemory routine [Kernel-Mode Driver Architecture], k109_63d9f0fb-d698-4707-9018-de2fa851a94b.xml, kernel.rtlzeromemory, wdm/RtlZeroMemory
ms.topic: macro
req.header: smclib.h
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlZeroMemory
product:
- Windows
targetos: Windows
req.typenames: SFFDISK_DPCMD
req.product: Windows 10 or later.
---

# RtlZeroMemory macro


## -description


The <b>RtlZeroMemory</b> routine fills a block of memory with zeros, given a pointer to the block and the length, in bytes, to be filled.


## -syntax


```cpp
VOID RtlZeroMemory(
  _Out_ VOID UNALIGNED *Destination,
  _In_  SIZE_T         Length
);
```


## -parameters




### -param d

<p>A pointer to the memory block to be filled with zeros.</p>


### -param c

<p>The number of bytes to fill with zeros.</p>






## -remarks



To zero out a memory buffer to erase security-sensitive data, use <a href="..\wdm\nf-wdm-rtlsecurezeromemory.md">RtlSecureZeroMemory</a> instead.

Callers of <b>RtlZeroMemory</b> can be running at any IRQL if the destination memory block is in nonpaged system memory. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.




## -see-also

<a href="..\wdm\nf-wdm-rtlfillmemory.md">RtlFillMemory</a>



<a href="..\wdm\nf-wdm-rtlsecurezeromemory.md">RtlSecureZeroMemory</a>



 

 



