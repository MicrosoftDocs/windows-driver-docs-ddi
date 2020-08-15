---
UID: NF:wdm.PoFxCompleteIdleCondition
title: PoFxCompleteIdleCondition function (wdm.h)
description: The PoFxCompleteIdleCondition routine informs the power management framework (PoFx) that the specified component has completed a pending change to the idle condition.
old-location: kernel\pofxcompleteidlecondition.htm
tech.root: kernel
ms.assetid: D43DA9A4-02F4-4C4E-83AE-DFADA0FCC73D
ms.date: 04/30/2018
keywords: ["PoFxCompleteIdleCondition function"]
ms.keywords: PoFxCompleteIdleCondition, PoFxCompleteIdleCondition routine [Kernel-Mode Driver Architecture], kernel.pofxcompleteidlecondition, wdm/PoFxCompleteIdleCondition
f1_keywords:
 - "wdm/PoFxCompleteIdleCondition"
 - "PoFxCompleteIdleCondition"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Ntoskrnl.exe
api_name:
- PoFxCompleteIdleCondition
targetos: Windows
req.typenames: 
---

# PoFxCompleteIdleCondition function


## -description


The <b>PoFxCompleteIdleCondition</b> routine informs the power management framework (PoFx) that the specified component has completed a pending change to the idle condition.


## -parameters




### -param Handle 
[in]
A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> routine.


### -param Component 
[in]
The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


## -remarks



After PoFx calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_condition_callback">ComponentIdleConditionCallback</a> callback routine, the driver must respond by calling <b>PoFxCompleteIdleCondition</b>.

When PoFx calls the driver's <i>ComponentIdleConditionCallback</i> routine, the driver initiates a transition to the idle condition in the specified component. After this transition is complete, the driver calls <b>PoFxCompleteIdleCondition</b> to notify PoFx. The <b>PoFxCompleteIdleCondition</b> call can occur either during or after the <i>ComponentIdleConditionCallback</i> call.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_condition_callback">ComponentIdleConditionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a>
 

 

