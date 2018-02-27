---
UID: NF:wdm.KeRaiseIrql
title: KeRaiseIrql macro
author: windows-driver-content
description: The KeRaiseIrql routine raises the hardware priority to the specified IRQL value, thereby masking off interrupts of equivalent or lower IRQL on the current processor.
old-location: kernel\keraiseirql.htm
old-project: kernel
ms.assetid: ee340d85-5a66-4773-b325-831257e9bfd8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeRaiseIrql, KeRaiseIrql routine [Kernel-Mode Driver Architecture], k105_66b09c47-8f95-41ee-8432-5784f306ad62.xml, kernel.keraiseirql, wdm/KeRaiseIrql
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
req.irql: Any level (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Hal.lib
-	Hal.dll
apiname:
-	KeRaiseIrql
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeRaiseIrql macro


## -description


The <b>KeRaiseIrql</b> routine raises the hardware priority to the specified IRQL value, thereby masking off interrupts of equivalent or lower IRQL on the current processor.


## -syntax


````
VOID KeRaiseIrql(
  _In_  KIRQL  NewIrql,
  _Out_ PKIRQL OldIrql
);
````


## -parameters




### -param a

TBD


### -param b

TBD






#### - NewIrql [in]

Specifies the new IRQL to which the hardware priority is to be raised.


#### - OldIrql [out]

Pointer to the storage for the original (unraised) IRQL value to be used in a subsequent call to <a href="..\wdm\nf-wdm-kelowerirql.md">KeLowerIrql</a>.


## -remarks



If the new IRQL is less than the current IRQL, a bug check occurs. Otherwise, the current IRQL is set to the specified value.

Callers of this routine can be running at any IRQL. Any caller should restore the original IRQL with <a href="..\wdm\nf-wdm-kelowerirql.md">KeLowerIrql</a> as soon as possible.

A call to <b>KeLowerIrql</b> is valid if it specifies <i>NewIrql</i> &lt;= <i>CurrentIrql</i>. A call to <b>KeRaiseIrql</b> is valid if the caller specifies <i>NewIrql</i> &gt;= <i>CurrentIrql</i>.




## -see-also

<a href="..\wdm\nf-wdm-kegetcurrentirql.md">KeGetCurrentIrql</a>



<a href="..\wdm\nf-wdm-kelowerirql.md">KeLowerIrql</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeRaiseIrql routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

