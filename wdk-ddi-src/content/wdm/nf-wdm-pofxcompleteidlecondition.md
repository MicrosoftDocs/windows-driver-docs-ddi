---
UID: NF:wdm.PoFxCompleteIdleCondition
title: PoFxCompleteIdleCondition function
author: windows-driver-content
description: The PoFxCompleteIdleCondition routine informs the power management framework (PoFx) that the specified component has completed a pending change to the idle condition.
old-location: kernel\pofxcompleteidlecondition.htm
old-project: kernel
ms.assetid: D43DA9A4-02F4-4C4E-83AE-DFADA0FCC73D
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PoFxCompleteIdleCondition, PoFxCompleteIdleCondition routine [Kernel-Mode Driver Architecture], kernel.pofxcompleteidlecondition, wdm/PoFxCompleteIdleCondition
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Ntoskrnl.exe
api_name:
-	PoFxCompleteIdleCondition
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoFxCompleteIdleCondition function


## -description


The <b>PoFxCompleteIdleCondition</b> routine informs the power management framework (PoFx) that the specified component has completed a pending change to the idle condition.


## -parameters




### -param Handle [in]

A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a> routine.


### -param Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439585">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


## -returns



None.




## -remarks



After PoFx calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh406420">ComponentIdleConditionCallback</a> callback routine, the driver must respond by calling <b>PoFxCompleteIdleCondition</b>.

When PoFx calls the driver's <i>ComponentIdleConditionCallback</i> routine, the driver initiates a transition to the idle condition in the specified component. After this transition is complete, the driver calls <b>PoFxCompleteIdleCondition</b> to notify PoFx. The <b>PoFxCompleteIdleCondition</b> call can occur either during or after the <i>ComponentIdleConditionCallback</i> call.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406420">ComponentIdleConditionCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439585">PO_FX_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a>
 

 

