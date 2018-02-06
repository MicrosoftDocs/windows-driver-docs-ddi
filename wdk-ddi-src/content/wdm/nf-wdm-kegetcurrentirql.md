---
UID: NF:wdm.KeGetCurrentIrql
title: KeGetCurrentIrql function
author: windows-driver-content
description: The KeGetCurrentIrql routine returns the current IRQL.
old-location: kernel\kegetcurrentirql.htm
old-project: kernel
ms.assetid: 63c33017-d827-4a8f-bb6f-fd13a2528e0c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeGetCurrentIrql routine [Kernel-Mode Driver Architecture], k105_04c845e8-a239-4400-8a5f-15996754494a.xml, kernel.kegetcurrentirql, KeGetCurrentIrql, wdm/KeGetCurrentIrql
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Hal.lib
-	Hal.dll
apiname:
-	KeGetCurrentIrql
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeGetCurrentIrql function


## -description


The <b>KeGetCurrentIrql</b> routine returns the current IRQL.


## -syntax


````
 KIRQL KeGetCurrentIrql(void);
````


## -parameters





## -returns


<b>KeGetCurrentIrql</b> returns the current IRQL.



## -see-also

<a href="..\wdm\nf-wdm-keraiseirql.md">KeRaiseIrql</a>

<a href="..\wdm\nf-wdm-keacquirespinlockatdpclevel.md">KeAcquireSpinLockAtDpcLevel</a>

<a href="..\wdm\nf-wdm-kelowerirql.md">KeLowerIrql</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeGetCurrentIrql routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

