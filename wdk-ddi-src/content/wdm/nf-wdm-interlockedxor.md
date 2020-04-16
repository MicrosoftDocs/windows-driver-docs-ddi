---
UID: NF:wdm.InterlockedXor
title: InterlockedXor function (wdm.h)
description: The InterlockedOr routine atomically computes a bitwise exclusive OR operation.
old-location: kernel\interlockedxor.htm
tech.root: kernel
ms.assetid: 3ddf62f1-ce5d-4d55-9964-8d1786ac2997
ms.date: 04/30/2018
keywords: ["InterlockedXor function"]
ms.keywords: InterlockedXor, InterlockedXor routine [Kernel-Mode Driver Architecture], k102_7b4b6df0-2179-4a6a-941d-5aaa95609cd8.xml, kernel.interlockedxor, wdm/InterlockedXor
f1_keywords:
 - "wdm/InterlockedXor"
req.header: wdm.h
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- InterlockedXor
product:
- Windows
targetos: Windows
req.typenames: 
---

# InterlockedXor function


## -description


The <b>InterlockedOr</b> routine atomically computes a bitwise exclusive OR operation.


## -parameters




### -param Destination [in, out]

A pointer to the variable to be exclusive ORed with <i>Value</i>. The result of the operation is stored in the variable. 


### -param Value [in]

Specifies the value to be exclusive ORed with the variable that is pointed to by <i>Destination</i>. 


## -returns



<b>InterlockedXor</b> returns the original value stored in the variable pointed to by <i>Destination</i>.




## -remarks



<b>InterlockedXor</b> atomically computes <b>*</b><i>Destination</i><b>^=</b><i>Value</i>. 

Interlocked operations cannot be used on non-cached memory. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedand">InterlockedAnd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedor">InterlockedOr</a>
 

 

