---
UID: NF:wdm.PoFxCompleteIdleState
title: PoFxCompleteIdleState function (wdm.h)
description: The PoFxCompleteIdleState routine informs the power management framework (PoFx) that the specified component has completed a pending change to an Fx state.
old-location: kernel\pofxcompleteidlestate.htm
tech.root: kernel
ms.assetid: D9224991-DB36-4250-861A-6C21E29F91EF
ms.date: 04/30/2018
keywords: ["PoFxCompleteIdleState function"]
ms.keywords: PoFxCompleteIdleState, PoFxCompleteIdleState routine [Kernel-Mode Driver Architecture], kernel.pofxcompleteidlestate, wdm/PoFxCompleteIdleState
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PoFxCompleteIdleState
 - wdm/PoFxCompleteIdleState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Ntoskrnl.exe
api_name:
 - PoFxCompleteIdleState
---

# PoFxCompleteIdleState function


## -description

The <b>PoFxCompleteIdleState</b> routine informs the power management framework (PoFx) that the specified component has completed a pending change to an Fx state.

## -parameters

### -param Handle 

[in]
A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> routine.

### -param Component 

[in]
The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

## -remarks

After PoFx calls the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_state_callback">ComponentIdleStateCallback</a> callback routine, the driver must respond by calling <b>PoFxCompleteIdleState</b>.

PoFx calls the driver's <i>ComponentIdleStateCallback</i> routine to tell the driver to switch the specified component to a new Fx power state. After the driver completes the transition to the new Fx state, the driver calls <b>PoFxCompleteIdleState</b> to inform PoFx. The <b>PoFxCompleteIdleState</b> call can occur either during or after the <i>ComponentIdleStateCallback</i> call.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_state_callback">ComponentIdleStateCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a>