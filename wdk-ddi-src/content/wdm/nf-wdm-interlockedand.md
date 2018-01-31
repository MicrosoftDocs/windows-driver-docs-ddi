---
UID: NF:wdm.InterlockedAnd
title: InterlockedAnd function
author: windows-driver-content
description: The InterlockedAnd macro atomically computes a bitwise AND operation.
old-location: kernel\interlockedand.htm
old-project: kernel
ms.assetid: 3b1ff981-7f87-4a47-81a3-3e323459c333
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k102_839df216-b391-436b-9e33-d60dfbb5dbe9.xml, InterlockedAnd function [Kernel-Mode Driver Architecture], InterlockedAnd, wdm/InterlockedAnd, kernel.interlockedand
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
-	InterlockedAnd
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# InterlockedAnd function


## -description


The <b>InterlockedAnd</b> macro atomically computes a bitwise AND operation.


## -syntax


````
LONG InterlockedAnd(
  _Inout_ LONG volatile *Destination,
  _In_    LONG          Value
);
````


## -parameters




#### - Destination [in, out]

A pointer to the variable to be ANDed with <i>Value</i>. The result of the operation is stored in the variable.


#### - Value [in]

Specifies the value to be ANDed with the variable that is pointed to by <i>Destination</i>. 


## -returns


<b>InterlockedAnd</b> returns the original value stored in the variable pointed to by <i>Destination</i>. 



## -remarks


<b>InterlockedAnd</b> atomically computes <b>*</b><i>Destination</i><b>&amp;=</b><i>Value</i>.

Interlocked operations cannot be used on non-cached memory. 



## -see-also

<a href="..\wdm\nf-wdm-interlockedxor.md">InterlockedXor</a>

<a href="..\wdm\nf-wdm-interlockedor.md">InterlockedOr</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InterlockedAnd function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

