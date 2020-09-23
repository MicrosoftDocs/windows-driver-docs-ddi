---
UID: NC:wdm.PO_FX_COMPONENT_IDLE_STATE_CALLBACK
title: PO_FX_COMPONENT_IDLE_STATE_CALLBACK (wdm.h)
description: The ComponentIdleStateCallback callback routine notifies the driver of a pending change to the Fx power state of the specified component.
old-location: kernel\componentidlestatecallback.htm
tech.root: kernel
ms.assetid: B98D14A1-7016-4299-9E7E-45E5EB6BE912
ms.date: 04/30/2018
keywords: ["PO_FX_COMPONENT_IDLE_STATE_CALLBACK callback function"]
ms.keywords: ComponentIdleStateCallback, ComponentIdleStateCallback routine [Kernel-Mode Driver Architecture], PO_FX_COMPONENT_IDLE_STATE_CALLBACK, kernel.componentidlestatecallback, wdm/ComponentIdleStateCallback
req.header: wdm.h
req.include-header: Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 8 and later versions of Windows.
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
req.lib: 
req.dll: 
req.irql: Called at IRQL <= DISPATCH_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - PO_FX_COMPONENT_IDLE_STATE_CALLBACK
 - wdm/PO_FX_COMPONENT_IDLE_STATE_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - ComponentIdleStateCallback
---

# PO_FX_COMPONENT_IDLE_STATE_CALLBACK callback function


## -description

The <i>ComponentIdleStateCallback</i> callback routine notifies the driver of a pending change to the Fx power state of the specified component.

## -parameters

### -param Context 

[in]
A pointer to the device context. The device driver uses this context to store information about the current power state of the device. The device driver specified this pointer in the <b>DeviceContext</b> member of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a> structure that the driver used to register the device with the power management framework (PoFx). This context is opaque to PoFx.

### -param Component 

[in]
Specifies the component number. This parameter is an index into the <b>Components</b> array in the <b>PO_FX_DEVICE</b> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N-1.

### -param State 

[in]
Specifies the new Fx power state that the component will change to. If this parameter is zero, the new state is F0; if this parameter is one, the new state is F1; and so on.

## -remarks

When PoFx calls the driver's <i>ComponentIdleStateCallback</i> routine, the driver might need to prepare for the pending Fx state change. After any necessary preparations are completed, the driver must call the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxcompleteidlestate">PoFxCompleteIdleState</a> routine to notify PoFx that the driver completed its response to the <i>ComponentIdleStateCallback</i> callback. The <b>PoFxCompleteIdleState</b> call can occur either before or after the <i>ComponentIdleStateCallback</i> routine returns.

If the component is to switch from F0 to a low-power Fx state in which the device will lose the hardware state of the component, the driver must save the component's hardware state before the transition to the new Fx state occurs. If the component is to switch from a low-power Fx state to F0, and the hardware state was previously saved, the driver should restore the hardware state after power is restored to the component.

For some devices, the power state of a component might be controlled in the device hardware. For these devices, the driver is typically responsible for changing the power state of the component. For other devices, the power state of a component might be controlled by hardware that is external to the device, and the driver typically must rely on PoFx to configure the power state of the component.

If the driver is responsible for configuring the power state of the component, the driver should change the power state in response to the <i>ComponentIdleStateCallback</i> callback. For a transition from F0 to a low-power Fx state, the component is in F0 on entry to the <i>ComponentIdleStateCallback</i> routine, and the driver must switch the component the new Fx state before calling <b>PoFxCompleteIdleState</b>. For a transition from a low-power Fx state to F0, the component is in the low-power Fx state on entry to the <i>ComponentIdleStateCallback</i> routine, and the driver must switch the component to F0 before calling <b>PoFxCompleteIdleState</b>.

If the driver is not responsible for configuring the power state of the component, the driver should assume that the component is always in the F0 state on entry to the <i>ComponentIdleStateCallback</i> routine. For a pending transition from F0 to a low-power Fx state, the transition to the new Fx state does not occur until after the driver calls <b>PoFxCompleteIdleState</b>. For a transition from a low-power Fx state to F0, the transition to F0 occurs before the <i>ComponentIdleStateCallback</i> routine is called.

PoFx never calls the <i>ComponentIdleStateCallback</i> routine to switch directly from one low-power Fx state to another low-power Fx state. For example, PoFx might need to switch a component from one low-power Fx state to another in response to a call to the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxsetcomponentlatency">PoFxSetComponentLatency</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxsetcomponentresidency">PoFxSetComponentResidency</a>, or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxsetcomponentwake">PoFxSetComponentWake</a> routine. In this case, PoFx first calls the <i>ComponentIdleStateCallback</i> routine to switch from the old Fx state to F0, and then calls the <i>ComponentIdleStateCallback</i> routine a second time to switch from F0 to the new Fx state.


#### Examples

To define a <i>ComponentIdleStateCallback</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ComponentIdleStateCallback</i> callback routine that is named <code>MyComponentIdleStateCallback</code>, use the PO_FX_COMPONENT_IDLE_STATE_CALLBACK type as shown in this code example:


```
PO_FX_COMPONENT_IDLE_STATE_CALLBACK MyComponentIdleStateCallback;
```

Then, implement your callback routine as follows:


```
_Use_decl_annotations_
VOID
  MyComponentIdleStateCallback(
    PVOID Context,
    ULONG Component,
    ULONG State
    )
  {
      // Function body
  }
```

The PO_FX_COMPONENT_IDLE_STATE_CALLBACK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the PO_FX_COMPONENT_IDLE_STATE_CALLBACK function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxcompleteidlestate">PoFxCompleteIdleState</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxsetcomponentlatency">PoFxSetComponentLatency</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxsetcomponentresidency">PoFxSetComponentResidency</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxsetcomponentwake">PoFxSetComponentWake</a>