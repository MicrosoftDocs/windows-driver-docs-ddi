---
UID: NF:wdm.KeLowerIrql~r1
title: KeLowerIrql function (wdm.h)
description: The KeLowerIrql routine restores the IRQL on the current processor to its original value.
old-location: kernel\kelowerirql.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KeLowerIrql function"]
ms.keywords: KeLowerIrql, KeLowerIrql routine [Kernel-Mode Driver Architecture], k105_06c56235-3b9e-4413-aadb-91e86898121d.xml, kernel.kelowerirql, wdm/KeLowerIrql
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
req.dll: NtosKrnl.exe
req.irql: Any level
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - KeLowerIrql
 - wdm/KeLowerIrql
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - NtosKrnl.exe
api_name:
 - KeLowerIrql
---

# KeLowerIrql function


## -description

The <b>KeLowerIrql</b> routine restores the IRQL on the current processor to its original value. For information about IRQLs, see [Managing Hardware Priorities](/windows-hardware/drivers/kernel/managing-hardware-priorities).

## -parameters

### -param NewIrql [in]

Specifies the IRQL that was returned from <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keraiseirql">KeRaiseIrql</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keraiseirqltodpclevel">KeRaiseIrqlToDpcLevel</a>.

## -remarks

It is a fatal error to call <b>KeLowerIrql</b> using an input <i>NewIrql</i> that was not returned by the immediately preceding call to <b>KeRaiseIrql</b> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keraiseirqltodpclevel">KeRaiseIrqlToDpcLevel</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetcurrentirql">KeGetCurrentIrql</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keraiseirql">KeRaiseIrql</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keraiseirqltodpclevel">KeRaiseIrqlToDpcLevel</a>
