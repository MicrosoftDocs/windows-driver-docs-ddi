---
UID: NF:wdm.KeRaiseIrqlToDpcLevel
title: KeRaiseIrqlToDpcLevel function
author: windows-driver-content
description: The KeRaiseIrqlToDpcLevel routine raises the hardware priority to IRQL = DISPATCH_LEVEL, thereby masking off interrupts of equivalent or lower IRQL on the current processor.
old-location: kernel\keraiseirqltodpclevel.htm
old-project: kernel
ms.assetid: ac82e003-ec05-4b8b-a4fb-64498fb17f9b
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeRaiseIrqlToDpcLevel, KeRaiseIrqlToDpcLevel routine [Kernel-Mode Driver Architecture], k105_64c33a5b-8efa-4d97-9569-2ea68a227d17.xml, kernel.keraiseirqltodpclevel, wdm/KeRaiseIrqlToDpcLevel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hal.lib
-	Hal.dll
api_name:
-	KeRaiseIrqlToDpcLevel
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeRaiseIrqlToDpcLevel function


## -description


The <b>KeRaiseIrqlToDpcLevel</b> routine raises the hardware priority to IRQL = DISPATCH_LEVEL, thereby masking off interrupts of equivalent or lower IRQL on the current processor.


## -parameters






## -returns



<b>KeRaiseIrqlToDpcLevel</b> returns the IRQL at which the call occurred.




## -remarks



Any caller of <b>KeRaiseIrqlToDpcLevel</b> should save the returned IRQL value. Every such caller must restore the original IRQL as quickly as possible by passing this returned IRQL in a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff552968">KeLowerIrql</a>.

Callers of <b>KeRaiseIrqlToDpcLevel</b> must be running at IRQL &lt;= DISPATCH_LEVEL. Otherwise, a call to this routine causes a bug check.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552054">KeGetCurrentIrql</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552968">KeLowerIrql</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553079">KeRaiseIrql</a>
 

 

