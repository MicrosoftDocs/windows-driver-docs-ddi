---
UID: NF:wdm.RtlUlonglongByteSwap
title: RtlUlonglongByteSwap macro
author: windows-driver-content
description: The RtlUlonglongByteSwap routine reverses the ordering of the eight bytes in a 64-bit unsigned integer value.
old-location: kernel\rtlulonglongbyteswap.htm
old-project: kernel
ms.assetid: 70d16119-ac78-40a2-995a-d20ca63c53c1
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: RtlUlonglongByteSwap, RtlUlonglongByteSwap routine [Kernel-Mode Driver Architecture], k109_e3102ade-bf90-43a5-831d-c4c215a6872c.xml, kernel.rtlulonglongbyteswap, wdm/RtlUlonglongByteSwap
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlUlonglongByteSwap
product: Windows
targetos: Windows
req.typenames: 
---

# RtlUlonglongByteSwap macro


## -description


The <b>RtlUlonglongByteSwap</b> routine reverses the ordering of the eight bytes in a 64-bit unsigned integer value.


## -parameters




### -param _x

TBD






#### - Source [in]

A ULONGLONG value to convert to a byte-swapped version.


## -remarks



For example, if the <i>Source</i> parameter value is 0x0123456789abcdef, the routine returns 0xefcdab8967452301.

A typical use of this routine is to convert a ULONGLONG value from little-endian byte format to big-endian byte format, and vice versa.

To reverse the ordering of bytes in a USHORT value, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563016">RtlUshortByteSwap</a> routine. To reverse ordering of bytes in a ULONG value, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562886">RtlUlongByteSwap</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562886">RtlUlongByteSwap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563016">RtlUshortByteSwap</a>
 

 

