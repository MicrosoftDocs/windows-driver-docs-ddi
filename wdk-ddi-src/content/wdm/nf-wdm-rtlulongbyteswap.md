---
UID: NF:wdm.RtlUlongByteSwap~r1
title: RtlUlongByteSwap macro (wdm.h)
description: The RtlUlongByteSwap routine reverses the ordering of the four bytes in a 32-bit unsigned integer value.
old-location: kernel\rtlulongbyteswap.htm
tech.root: kernel
ms.assetid: 4c08a70e-5092-40fb-94fd-c3ef8a5537b5
ms.date: 04/30/2018
keywords: ["RtlUlongByteSwap macro"]
ms.keywords: RtlUlongByteSwap, RtlUlongByteSwap routine [Kernel-Mode Driver Architecture], k109_0d4753a3-859a-429f-bd07-66669f1b46e8.xml, kernel.rtlulongbyteswap, wdm/RtlUlongByteSwap
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlUlongByteSwap
 - wdm/RtlUlongByteSwap
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlUlongByteSwap
---

# RtlUlongByteSwap macro


## -description

The <b>RtlUlongByteSwap</b> routine reverses the ordering of the four bytes in a 32-bit unsigned integer value.

## -parameters

### -param Source 

[in]
A ULONG value to convert to a byte-swapped version.

## -returns

The byte-swapped version of the Source input parameter value.

## -remarks

For example, if the <i>Source</i> parameter value is 0x12345678, the routine returns 0x78563412.

A typical use of this routine is to convert a ULONG value from little-endian byte format to big-endian byte format, and vice versa.

Use this routine instead of <b>ntohl</b> or <b>htonl</b>.

To reverse the ordering of bytes in a USHORT value, use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlushortbyteswap">RtlUshortByteSwap</a> routine. To reverse ordering of bytes in a ULONGLONG value, use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlulonglongbyteswap">RtlUlonglongByteSwap</a> routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlulonglongbyteswap">RtlUlonglongByteSwap</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlushortbyteswap">RtlUshortByteSwap</a>