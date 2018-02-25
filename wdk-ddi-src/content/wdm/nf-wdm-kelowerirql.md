---
UID: NF:wdm.KeLowerIrql
title: KeLowerIrql macro
author: windows-driver-content
description: The KeLowerIrql routine restores the IRQL on the current processor to its original value.
old-location: kernel\kelowerirql.htm
old-project: kernel
ms.assetid: 95598654-71dd-41cc-a663-b0bcaee77687
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , I, K, KeLowerIrql, KeLowerIrql routine [Kernel-Mode Driver Architecture], L, e, k105_06c56235-3b9e-4413-aadb-91e86898121d.xml, kernel.kelowerirql, l, o, q, r, w, wdm/KeLowerIrql"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Hal.lib
-	Hal.dll
apiname:
-	KeLowerIrql
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeLowerIrql macro


## -description


The <b>KeLowerIrql</b> routine restores the IRQL on the current processor to its original value.


## -syntax


````
 VOID KeLowerIrql(
  _In_ KIRQL NewIrql
);
````


## -parameters




### -param a

TBD






#### - NewIrql [in]

Specifies the IRQL that was returned from <a href="..\wdm\nf-wdm-keraiseirql.md">KeRaiseIrql</a> or <a href="..\ntddk\nf-ntddk-keraiseirqltodpclevel.md">KeRaiseIrqlToDpcLevel</a>.


## -remarks



It is a fatal error to call <b>KeLowerIrql</b> using an input <i>NewIrql</i> that was not returned by the immediately preceding call to <b>KeRaiseIrql</b> or <a href="..\ntddk\nf-ntddk-keraiseirqltodpclevel.md">KeRaiseIrqlToDpcLevel</a>.




## -see-also

<a href="..\ntddk\nf-ntddk-keraiseirqltodpclevel.md">KeRaiseIrqlToDpcLevel</a>



<a href="..\wdm\nf-wdm-kegetcurrentirql.md">KeGetCurrentIrql</a>



<a href="..\wdm\nf-wdm-keraiseirql.md">KeRaiseIrql</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeLowerIrql routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

