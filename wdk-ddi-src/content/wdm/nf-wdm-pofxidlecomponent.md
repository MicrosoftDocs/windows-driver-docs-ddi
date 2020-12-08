---
UID: NF:wdm.PoFxIdleComponent
title: PoFxIdleComponent function (wdm.h)
description: The PoFxIdleComponent routine decrements the activation reference count on the specified component.
old-location: kernel\pofxidlecomponent.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PoFxIdleComponent function"]
ms.keywords: PoFxIdleComponent, PoFxIdleComponent routine [Kernel-Mode Driver Architecture], kernel.pofxidlecomponent, wdm/PoFxIdleComponent
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
 - PoFxIdleComponent
 - wdm/PoFxIdleComponent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Ntoskrnl.exe
api_name:
 - PoFxIdleComponent
---

# PoFxIdleComponent function


## -description

The <b>PoFxIdleComponent</b> routine decrements the activation reference count on the specified component.

## -parameters

### -param Handle 

[in]
A handle that represents the registration of the device with the power management framework (PoFx). The device driver previously received this handle from the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> routine.

### -param Component 

[in]
The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

### -param Flags 

[in]
The flags for the idle operation. Set this member to zero or to one of the following flag <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxissuecomponentperfstatechange">PO_FX_FLAG_XXX</a> bits:

<ul>
<li><b>PO_FX_FLAG_BLOCKING</b></li>
<li><b>PO_FX_FLAG_ASYNC_ONLY</b></li>
</ul>
These two flag bits are mutually exclusive. For more information, see Remarks.

## -remarks

A device driver calls <b>PoFxIdleComponent</b> to release an activation reference to a component in a device. The driver obtained the activation reference in a previous call to the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxactivatecomponent">PoFxActivateComponent</a> routine. The driver should hold an activation reference on a component only while the driver needs to access the component. To hold an activation reference on a component that is not being used prevents the component from entering a low-power Fx state.

If the driver holds no other activation references to the component, <b>PoFxIdleComponent</b> initiates a transition from the active condition to the idle condition. When this transition completes, PoFx calls the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_condition_callback">ComponentIdleConditionCallback</a> routine to notify the driver. If the driver retains one or more additional activation references on the component, the component stays in the active condition, and the <i>ComponentIdleConditionCallback</i> routine is not called.

PoFx maintains an activation reference count for each component in the device. The <b>PoFxActivateComponent</b> routine increments this count, and <b>PoFxIdleComponent</b> decrements it. The component remains in the active condition while this count is nonzero. When the driver releases its last activation reference to a component, the count decrements to zero and the component enters the idle condition. After the component enters the idle condition, PoFx can potentially switch the component to a low-power Fx state. For more information, see <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxactivatecomponent">PoFxActivateComponent</a>.

If <i>Flags</i> = <b>PO_FX_FLAG_BLOCKING</b>, the <b>PoFxIdleComponent</b> call is synchronous. In this case, <b>PoFxIdleComponent</b> waits to return until the component completes the transition to the idle condition. <b>PoFxIdleComponent</b> calls the driver's <i>ComponentIdleConditionCallback</i> callback routine to inform the driver that the component is in the idle condition. This callback occurs in the same thread as the call to <b>PoFxIdleComponent</b>, and <b>PoFxIdleComponent</b> returns only after the <i>ComponentIdleConditionCallback</i> callback returns.

If <i>Flags</i> = <b>PO_FX_FLAG_ASYNC_ONLY</b>, the <b>PoFxIdleComponent</b> call is asynchronous. In this case, <b>PoFxIdleComponent</b> schedules the <i>ComponentIdleConditionCallback</i> callback to occur in another thread, and then returns without waiting for the callback to occur. The callback can occur before or after <b>PoFxIdleComponent</b> returns. The driver should rely on the <i>ComponentIdleConditionCallback</i> callback to determine when the component completes the transition to the idle condition. Until this callback occurs, the driver should assume that the component might still be in the active condition.

The driver can set <i>Flags</i> = 0 to indicate that it does not care whether the <b>PoFxIdleComponent</b> call is synchronous or asynchronous. In this case, PoFx decides whether to make the call synchronous or asynchronous.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_condition_callback">ComponentIdleConditionCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxissuecomponentperfstatechange">PO_FX_FLAG_XXX</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxactivatecomponent">PoFxActivateComponent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a>
