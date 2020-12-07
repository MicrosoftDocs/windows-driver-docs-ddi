---
UID: NF:wdm.RtlUshortByteSwap~r1
title: RtlUshortByteSwap macro (wdm.h)
description: The RtlUshortByteSwap routine reverses the ordering of the two bytes in a 16-bit unsigned integer value.
old-location: kernel\rtlushortbyteswap.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlUshortByteSwap macro"]
ms.keywords: RtlUshortByteSwap, RtlUshortByteSwap routine [Kernel-Mode Driver Architecture], k109_36a00506-f4e3-467b-9494-c13b2ea70a1f.xml, kernel.rtlushortbyteswap, wdm/RtlUshortByteSwap
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
 - RtlUshortByteSwap
 - wdm/RtlUshortByteSwap
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlUshortByteSwap
---

# RtlUshortByteSwap macro


## -description

The <b>RtlUshortByteSwap</b> routine reverses the ordering of the two bytes in a 16-bit unsigned integer value.

## -parameters

### -param Source 

[in]
A USHORT value to convert to a byte-swapped version.

## -returns

The byte-swapped version of the input parameter value.

## -remarks

For example, if the <i>Source</i> parameter value is 0x1234, the routine returns 0x3412.

A typical use of this routine is to convert a USHORT value from little-endian byte format to big-endian byte format, and vice versa.

Use this routine instead of <b>ntohs</b> or <b>htons</b>.

To reverse the ordering of bytes in a ULONG value, use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlulongbyteswap">RtlUlongByteSwap</a> routine. To reverse ordering of bytes in a ULONGLONG value, use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlulonglongbyteswap">RtlUlonglongByteSwap</a> routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlulongbyteswap">RtlUlongByteSwap</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlulonglongbyteswap">RtlUlonglongByteSwap</a>
