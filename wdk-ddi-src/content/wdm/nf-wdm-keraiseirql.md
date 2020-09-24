---
UID: NF:wdm.KeRaiseIrql
title: KeRaiseIrql macro (wdm.h)
description: The KeRaiseIrql routine raises the hardware priority to the specified IRQL value, thereby masking off interrupts of equivalent or lower IRQL on the current processor.
old-location: kernel\keraiseirql.htm
tech.root: kernel
ms.assetid: ee340d85-5a66-4773-b325-831257e9bfd8
ms.date: 04/30/2018
keywords: ["KeRaiseIrql macro"]
ms.keywords: KeRaiseIrql, KeRaiseIrql routine [Kernel-Mode Driver Architecture], k105_66b09c47-8f95-41ee-8432-5784f306ad62.xml, kernel.keraiseirql, wdm/KeRaiseIrql
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
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - KeRaiseIrql
 - wdm/KeRaiseIrql
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - NtosKrnl.exe
api_name:
 - KeRaiseIrql
---

# KeRaiseIrql macro


## -description

The <b>KeRaiseIrql</b> routine raises the hardware priority to the specified IRQL value, thereby masking off interrupts of equivalent or lower IRQL on the current processor. For information about IRQLs, see [Managing Hardware Priorities](/windows-hardware/drivers/kernel/managing-hardware-priorities).

## -parameters

### -param a 

[in]
The **NewIrql** parameter specifies the new KIRQL value to which the hardware priority is to be raised.

### -param b 

[out]
The **OldIrql** parameter is a pointer to the storage for the original (unraised) KIRQL value to be used in a subsequent call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kelowerirql">KeLowerIrql</a>.

## -syntax

```cpp
VOID KeRaiseIrql(
  _In_  KIRQL  NewIrql,
  _Out_ PKIRQL OldIrql
);
```

## -remarks

If the new IRQL is less than the current IRQL, a bug check occurs. Otherwise, the current IRQL is set to the specified value.

Callers of this routine can be running at any IRQL. Any caller should restore the original IRQL with <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kelowerirql">KeLowerIrql</a> as soon as possible.

A call to <b>KeLowerIrql</b> is valid if it specifies <i>NewIrql</i> <= <i>CurrentIrql</i>. A call to <b>KeRaiseIrql</b> is valid if the caller specifies <i>NewIrql</i> >= <i>CurrentIrql</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetcurrentirql">KeGetCurrentIrql</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kelowerirql~r1">KeLowerIrql</a>