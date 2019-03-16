---
UID: NF:wdm.RtlFindMostSignificantBit
title: RtlFindMostSignificantBit function (wdm.h)
description: The RtlFindMostSignificantBit routine returns the zero-based position of the most significant nonzero bit in its parameter.
old-location: kernel\rtlfindmostsignificantbit.htm
tech.root: kernel
ms.assetid: 372a155f-e270-49ab-a5ab-9b933b29ed74
ms.date: 04/30/2018
ms.keywords: RtlFindMostSignificantBit, RtlFindMostSignificantBit routine [Kernel-Mode Driver Architecture], k109_c8dcb9dd-ec2c-4b0c-92f2-167dcee10a96.xml, kernel.rtlfindmostsignificantbit, wdm/RtlFindMostSignificantBit
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlFindMostSignificantBit
product:
- Windows
targetos: Windows
req.typenames: 
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
 

 

