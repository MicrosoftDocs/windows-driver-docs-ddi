---
UID: NF:wdm.RtlFindMostSignificantBit
title: RtlFindMostSignificantBit function
author: windows-driver-content
description: The RtlFindMostSignificantBit routine returns the zero-based position of the most significant nonzero bit in its parameter.
old-location: kernel\rtlfindmostsignificantbit.htm
old-project: kernel
ms.assetid: 372a155f-e270-49ab-a5ab-9b933b29ed74
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlFindMostSignificantBit, RtlFindMostSignificantBit routine [Kernel-Mode Driver Architecture], k109_c8dcb9dd-ec2c-4b0c-92f2-167dcee10a96.xml, kernel.rtlfindmostsignificantbit, wdm/RtlFindMostSignificantBit
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
-	RtlFindMostSignificantBit
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlFindMostSignificantBit function


## -description


The <b>RtlFindMostSignificantBit</b> routine returns the zero-based position of the most significant nonzero bit in its parameter.


## -parameters




### -param Set [in]

The 64-bit value to be searched for its most significant nonzero bit. 


## -returns



The zero-based bit position of the most significant nonzero bit, or -1 if every bit is zero.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561880">RtlFindLeastSignificantBit</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlFindMostSignificantBit routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

