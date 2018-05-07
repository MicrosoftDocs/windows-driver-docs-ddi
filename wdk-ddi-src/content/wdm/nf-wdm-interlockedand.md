---
UID: NF:wdm.InterlockedAnd
title: InterlockedAnd function
author: windows-driver-content
description: The InterlockedAnd macro atomically computes a bitwise AND operation.
old-location: kernel\interlockedand.htm
old-project: kernel
ms.assetid: 3b1ff981-7f87-4a47-81a3-3e323459c333
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: InterlockedAnd, InterlockedAnd function [Kernel-Mode Driver Architecture], k102_839df216-b391-436b-9e33-d60dfbb5dbe9.xml, kernel.interlockedand, wdm/InterlockedAnd
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	InterlockedAnd
product:
- Windows
targetos: Windows
req.typenames: 
---

# InterlockedAnd function


## -description


The <b>InterlockedAnd</b> macro atomically computes a bitwise AND operation.


## -parameters




### -param Destination [in, out]

A pointer to the variable to be ANDed with <i>Value</i>. The result of the operation is stored in the variable.


### -param Value [in]

Specifies the value to be ANDed with the variable that is pointed to by <i>Destination</i>. 


## -returns



<b>InterlockedAnd</b> returns the original value stored in the variable pointed to by <i>Destination</i>. 




## -remarks



<b>InterlockedAnd</b> atomically computes <b>*</b><i>Destination</i><b>&amp;=</b><i>Value</i>.

Interlocked operations cannot be used on non-cached memory. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547928">InterlockedOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547933">InterlockedXor</a>
 

 

