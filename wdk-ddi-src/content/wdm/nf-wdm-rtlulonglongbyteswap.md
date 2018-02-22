---
UID: NF:wdm.RtlUlonglongByteSwap
title: RtlUlonglongByteSwap macro
author: windows-driver-content
description: The RtlUlonglongByteSwap routine reverses the ordering of the eight bytes in a 64-bit unsigned integer value.
old-location: kernel\rtlulonglongbyteswap.htm
old-project: kernel
ms.assetid: 70d16119-ac78-40a2-995a-d20ca63c53c1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wdm/RtlUlonglongByteSwap, RtlUlonglongByteSwap routine [Kernel-Mode Driver Architecture], RtlUlonglongByteSwap, kernel.rtlulonglongbyteswap, k109_e3102ade-bf90-43a5-831d-c4c215a6872c.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlUlonglongByteSwap
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlUlonglongByteSwap macro


## -description


The <b>RtlUlonglongByteSwap</b> routine reverses the ordering of the eight bytes in a 64-bit unsigned integer value.


## -syntax


````
ULONGLONG RtlUlonglongByteSwap(
  _In_ ULONGLONG Source
);
````


## -parameters




### -param _x

TBD






#### - Source [in]

A ULONGLONG value to convert to a byte-swapped version.


## -remarks



For example, if the <i>Source</i> parameter value is 0x0123456789abcdef, the routine returns 0xefcdab8967452301.

A typical use of this routine is to convert a ULONGLONG value from little-endian byte format to big-endian byte format, and vice versa.

To reverse the ordering of bytes in a USHORT value, use the <a href="..\wdm\nf-wdm-rtlushortbyteswap.md">RtlUshortByteSwap</a> routine. To reverse ordering of bytes in a ULONG value, use the <a href="..\wdm\nf-wdm-rtlulongbyteswap.md">RtlUlongByteSwap</a> routine.




## -see-also

<a href="..\wdm\nf-wdm-rtlulongbyteswap.md">RtlUlongByteSwap</a>



<a href="..\wdm\nf-wdm-rtlushortbyteswap.md">RtlUshortByteSwap</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUlonglongByteSwap routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

