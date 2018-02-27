---
UID: NF:miniport.InterlockedOr
title: InterlockedOr function
author: windows-driver-content
description: The InterlockedOr routine atomically computes a bitwise OR operation.
old-location: kernel\interlockedor.htm
old-project: kernel
ms.assetid: 1f66d3ed-7215-4fb5-87df-4489c3cd03c6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: InterlockedOr, InterlockedOr routine [Kernel-Mode Driver Architecture], k102_05d8ca48-ab6f-46ae-b026-cb2aaf6f37aa.xml, kernel.interlockedor, wdm/InterlockedOr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	InterlockedOr
product: Windows
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---

# InterlockedOr function


## -description


The <b>InterlockedOr</b> routine atomically computes a bitwise OR operation.


## -syntax


````
LONG InterlockedOr(
  _Inout_ LONG volatile *Destination,
  _In_    LONG          Value
);
````


## -parameters




### -param Destination [in, out]

A pointer to the variable to be ORed with <i>Value</i>. The result of the operation is stored in the variable.


### -param Value [in]

Specifies the value to be ORed with the variable that is pointed to by <i>Destination</i>. 


## -returns



<b>InterlockedOr</b> returns the original value stored in the variable pointed to by <i>Destination</i>. 




## -remarks



<b>InterlockedOr</b> atomically computes <b>*</b><i>Destination</i><b>|=</b><i>Value</i>. 

Interlocked operations cannot be used on non-cached memory. 




## -see-also

<a href="..\wdm\nf-wdm-interlockedxor.md">InterlockedXor</a>



<a href="..\wdm\nf-wdm-interlockedand.md">InterlockedAnd</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InterlockedOr routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

