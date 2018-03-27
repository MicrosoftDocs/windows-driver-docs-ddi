---
UID: NF:wdm.RtlUshortByteSwap
title: RtlUshortByteSwap macro
author: windows-driver-content
description: The RtlUshortByteSwap routine reverses the ordering of the two bytes in a 16-bit unsigned integer value.
old-location: kernel\rtlushortbyteswap.htm
old-project: kernel
ms.assetid: 83f6a599-0b35-4a02-b20f-80abcc6eae4f
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlUshortByteSwap, RtlUshortByteSwap routine [Kernel-Mode Driver Architecture], k109_36a00506-f4e3-467b-9494-c13b2ea70a1f.xml, kernel.rtlushortbyteswap, wdm/RtlUshortByteSwap
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
-	RtlUshortByteSwap
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlUshortByteSwap macro


## -description


The <b>RtlUshortByteSwap</b> routine reverses the ordering of the two bytes in a 16-bit unsigned integer value.


## -parameters




### -param _x

TBD






#### - Source [in]

A USHORT value to convert to a byte-swapped version.


## -remarks



For example, if the <i>Source</i> parameter value is 0x1234, the routine returns 0x3412.

A typical use of this routine is to convert a USHORT value from little-endian byte format to big-endian byte format, and vice versa.

Use this routine instead of <b>ntohs</b> or <b>htons</b>.

To reverse the ordering of bytes in a ULONG value, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562886">RtlUlongByteSwap</a> routine. To reverse ordering of bytes in a ULONGLONG value, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562890">RtlUlonglongByteSwap</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562886">RtlUlongByteSwap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562890">RtlUlonglongByteSwap</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUshortByteSwap routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

