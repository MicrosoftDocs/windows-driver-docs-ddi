---
UID: NF:wdm.KeLowerIrql
title: KeLowerIrql macro
author: windows-driver-content
description: The KeLowerIrql routine restores the IRQL on the current processor to its original value.
old-location: kernel\kelowerirql.htm
old-project: kernel
ms.assetid: 95598654-71dd-41cc-a663-b0bcaee77687
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeLowerIrql, KeLowerIrql routine [Kernel-Mode Driver Architecture], k105_06c56235-3b9e-4413-aadb-91e86898121d.xml, kernel.kelowerirql, wdm/KeLowerIrql
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
req.ddi-compliance: IrqlKeRaiseLower, IrqlKeRaiseLower2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hal.lib
-	Hal.dll
api_name:
-	KeLowerIrql
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeLowerIrql macro


## -description


The <b>KeLowerIrql</b> routine restores the IRQL on the current processor to its original value. For information about IRQLs, see [Managing Hardware Priorities](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/managing-hardware-priorities).


## -parameters




### -param a [in]

Specifies the IRQL that was returned from <a href="https://msdn.microsoft.com/library/windows/hardware/ff553079">KeRaiseIrql</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553084">KeRaiseIrqlToDpcLevel</a>.




## -remarks



It is a fatal error to call <b>KeLowerIrql</b> using an input <i>NewIrql</i> that was not returned by the immediately preceding call to <b>KeRaiseIrql</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553084">KeRaiseIrqlToDpcLevel</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552054">KeGetCurrentIrql</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553079">KeRaiseIrql</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553084">KeRaiseIrqlToDpcLevel</a>
 

 

