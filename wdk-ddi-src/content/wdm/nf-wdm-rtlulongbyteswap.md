---
UID: NF:wdm.RtlUlongByteSwap
title: RtlUlongByteSwap macro
author: windows-driver-content
description: The RtlUlongByteSwap routine reverses the ordering of the four bytes in a 32-bit unsigned integer value.
old-location: kernel\rtlulongbyteswap.htm
old-project: kernel
ms.assetid: 4c08a70e-5092-40fb-94fd-c3ef8a5537b5
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlUlongByteSwap, RtlUlongByteSwap routine [Kernel-Mode Driver Architecture], k109_0d4753a3-859a-429f-bd07-66669f1b46e8.xml, kernel.rtlulongbyteswap, wdm/RtlUlongByteSwap
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
-	RtlUlongByteSwap
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlUlongByteSwap macro


## -description


The <b>RtlUlongByteSwap</b> routine reverses the ordering of the four bytes in a 32-bit unsigned integer value.


## -parameters




### -param _x

TBD






#### - Source [in]

A ULONG value to convert to a byte-swapped version.


## -remarks



For example, if the <i>Source</i> parameter value is 0x12345678, the routine returns 0x78563412.

A typical use of this routine is to convert a ULONG value from little-endian byte format to big-endian byte format, and vice versa.

Use this routine instead of <b>ntohl</b> or <b>htonl</b>.

To reverse the ordering of bytes in a USHORT value, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563016">RtlUshortByteSwap</a> routine. To reverse ordering of bytes in a ULONGLONG value, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562890">RtlUlonglongByteSwap</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562890">RtlUlonglongByteSwap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563016">RtlUshortByteSwap</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUlongByteSwap routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

