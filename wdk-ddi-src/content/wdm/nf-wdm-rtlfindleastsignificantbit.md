---
UID: NF:wdm.RtlFindLeastSignificantBit
title: RtlFindLeastSignificantBit function (wdm.h)
description: The RtlFindLeastSignificantBit routine returns the zero-based position of the least significant nonzero bit in its parameter.
old-location: kernel\rtlfindleastsignificantbit.htm
tech.root: kernel
ms.assetid: fb260c9b-dece-49ef-9701-d5198b8a08fb
ms.date: 04/30/2018
ms.keywords: RtlFindLeastSignificantBit, RtlFindLeastSignificantBit routine [Kernel-Mode Driver Architecture], k109_c7ab87ad-4b9e-40f5-87fb-25ced2ec0dd8.xml, kernel.rtlfindleastsignificantbit, wdm/RtlFindLeastSignificantBit
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
-	RtlFindLeastSignificantBit
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlFindLeastSignificantBit function


## -description


The <b>RtlFindLeastSignificantBit</b> routine returns the zero-based position of the least significant nonzero bit in its parameter.


## -parameters




### -param Set [in]

The 64-bit value to be searched for its least significant nonzero bit. 


## -returns



The zero-based bit position of the least significant nonzero bit, or -1 if every bit is zero.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561883">RtlFindMostSignificantBit</a>
 

 

