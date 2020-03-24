---
UID: NF:wdm.KeGetCurrentIrql
title: KeGetCurrentIrql function (wdm.h)
description: The KeGetCurrentIrql routine returns the current IRQL.
old-location: kernel\kegetcurrentirql.htm
tech.root: kernel
ms.assetid: 63c33017-d827-4a8f-bb6f-fd13a2528e0c
ms.date: 04/30/2018
keywords: ["KeGetCurrentIrql function"]
ms.keywords: KeGetCurrentIrql, KeGetCurrentIrql routine [Kernel-Mode Driver Architecture], k105_04c845e8-a239-4400-8a5f-15996754494a.xml, kernel.kegetcurrentirql, wdm/KeGetCurrentIrql
f1_keywords:
 - "wdm/KeGetCurrentIrql"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Hal.lib
- Hal.dll
api_name:
- KeGetCurrentIrql
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeGetCurrentIrql function


## -description


The <b>KeGetCurrentIrql</b> routine returns the current IRQL. For information about IRQLs, see [Managing Hardware Priorities](https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-hardware-priorities).


## -returns



<b>KeGetCurrentIrql</b> returns the current IRQL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlockatdpclevel">KeAcquireSpinLockAtDpcLevel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kelowerirql">KeLowerIrql</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keraiseirql">KeRaiseIrql</a>


 
[Managing Hardware Priorities](https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-hardware-priorities)
 

