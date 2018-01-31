---
UID: NF:wdm.RtlFindLeastSignificantBit
title: RtlFindLeastSignificantBit function
author: windows-driver-content
description: The RtlFindLeastSignificantBit routine returns the zero-based position of the least significant nonzero bit in its parameter.
old-location: kernel\rtlfindleastsignificantbit.htm
old-project: kernel
ms.assetid: fb260c9b-dece-49ef-9701-d5198b8a08fb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlfindleastsignificantbit, k109_c7ab87ad-4b9e-40f5-87fb-25ced2ec0dd8.xml, wdm/RtlFindLeastSignificantBit, RtlFindLeastSignificantBit routine [Kernel-Mode Driver Architecture], RtlFindLeastSignificantBit
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlFindLeastSignificantBit
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlFindLeastSignificantBit function


## -description


The <b>RtlFindLeastSignificantBit</b> routine returns the zero-based position of the least significant nonzero bit in its parameter.


## -syntax


````
CCHAR RtlFindLeastSignificantBit(
  _In_ ULONGLONG Set
);
````


## -parameters




#### - Set [in]

The 64-bit value to be searched for its least significant nonzero bit. 


## -returns


The zero-based bit position of the least significant nonzero bit, or -1 if every bit is zero.



## -see-also

<a href="..\wdm\nf-wdm-rtlfindmostsignificantbit.md">RtlFindMostSignificantBit</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlFindLeastSignificantBit routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

