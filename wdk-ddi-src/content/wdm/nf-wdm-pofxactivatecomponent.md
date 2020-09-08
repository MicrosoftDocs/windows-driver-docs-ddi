---
UID: NF:wdm.PoFxActivateComponent
title: PoFxActivateComponent function (wdm.h)
description: The PoFxActivateComponent routine increments the activation reference count on the specified component.
old-location: kernel\pofxactivatecomponent.htm
tech.root: kernel
ms.assetid: B964B836-68C1-4254-963C-8D46ACE64107
ms.date: 04/30/2018
keywords: ["PoFxActivateComponent function"]
ms.keywords: PO_FX_FLAG_ASYNC_ONLY, PO_FX_FLAG_BLOCKING, PoFxActivateComponent, PoFxActivateComponent routine [Kernel-Mode Driver Architecture], kernel.pofxactivatecomponent, wdm/PoFxActivateComponent
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
 - PoFxActivateComponent
 - wdm/PoFxActivateComponent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Ntoskrnl.exe
api_name:
 - PoFxActivateComponent
---

# PoFxActivateComponent function


## -description

The <b>PoFxActivateComponent</b> routine increments the activation reference count on the specified component.

## -parameters

### -param Handle 

[in]
A handle that represents the registration of the device with the power management framework (PoFx). The device driver previously received this handle from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> routine.

### -param Component 

[in]
The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

### -param Flags 

[in]
The flags for the activation operation. Set this member to zero or to one of the following flag <b>PO_FX_FLAG_<i>XXX</i></b> bits:

These two flag bits are mutually exclusive. For more information, see Remarks.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="PO_FX_FLAG_BLOCKING"></a><a id="po_fx_flag_blocking"></a><dl>
<dt><b>PO_FX_FLAG_BLOCKING</b></dt>
<dt>0x1</dt>
</dl>
</td>
<td width="60%">
Make the condition change synchronous. If this flag is set, the routine that requests the condition change does not return control to the calling driver until the component hardware completes the transition to the new condition. This flag can be used only if the caller is running at IRQL < DISPATCH_LEVEL.

</td>
</tr>
<tr>
<td width="40%"><a id="PO_FX_FLAG_ASYNC_ONLY"></a><a id="po_fx_flag_async_only"></a><dl>
<dt><b>PO_FX_FLAG_ASYNC_ONLY</b></dt>
<dt>0x2</dt>
</dl>
</td>
<td width="60%">
Make the condition change fully asynchronous. If this flag is set, the calling driver's callback routine is called from a thread other than the thread in which the routine that requests the condition change is called. Thus, the routine that requests the condition change always returns asynchronously without waiting for the callback to complete.

</td>
</tr>
</table>

## -remarks

Before a device driver can access a component in a device, the driver must first call <b>PoFxActivateComponent</b> to obtain an activation reference to the component. If the component is not already in the active condition, this call initiates a transition from the idle condition to the active condition. When this transition completes, PoFx calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_active_condition_callback">ComponentActiveConditionCallback</a> routine to notify the driver. The driver can access the hardware registers in a component only when the component is in the active condition.

If the component is already in the active condition when <b>PoFxActivateComponent</b> is called, no transition is required, and the <i>ComponentActiveConditionCallback</i> routine is not called.

After a component enters the active condition, it remains in the active condition for as long as the driver holds one or more activation references on the component. To release an activation reference, the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxidlecomponent">PoFxIdleComponent</a> routine. When the driver releases the last activation reference on a component, <b>PoFxIdleComponent</b> initiates a transition from the active condition to the idle condition. A component that is in the idle condition can potentially enter a low-power Fx state.

If <i>Flags</i> = <b>PO_FX_FLAG_BLOCKING</b>, the <b>PoFxActivateComponent</b> call is synchronous. If the component is already in the active condition, the call increments the activation reference count and returns without waiting. Otherwise, <b>PoFxActivateComponent</b> waits to return until the component completes the transition to the active condition. In this case, if the component is not already in the F0 state when the call occurs, <b>PoFxActivateComponent</b> calls the driver's <i>ComponentIdleStateCallback</i> routine to initiate the transition to F0. After the component enters the F0 state, <b>PoFxActivateComponent</b> calls the driver's <i>ComponentActiveConditionCallback</i> routine to inform the driver that the component is in the active condition. These callbacks occur in the same thread as the call to <b>PoFxActivateComponent</b>, and <b>PoFxActivateComponent</b> returns only after the <i>ComponentActiveConditionCallback</i> callback returns.

If <i>Flags</i> = <b>PO_FX_FLAG_ASYNC_ONLY</b>, the <b>PoFxActivateComponent</b> call is asynchronous. If the component is already in the active condition, the call increments the activation reference count and returns. Otherwise, <b>PoFxActivateComponent</b> schedules the <i>ComponentIdleStateCallback</i> (if necessary) and <i>ComponentActiveConditionCallback</i> callbacks to occur in another thread, and then returns without waiting for either callback to occur. The callbacks can occur before or after <b>PoFxActivateComponent</b> returns. The driver relies on the <i>ComponentActiveConditionCallback</i> callback to determine when the component completes the transition to the active condition.

The driver can set <i>Flags</i> = 0 to indicate that it does not care whether the <b>PoFxActivateComponent</b> call is synchronous or asynchronous. In this case, PoFx decides whether to make the call synchronous or asynchronous.

Two or more code paths in the same driver might need to concurrently access a particular component. The <b>PoFxActivateComponent</b> and <b>PoFxIdleComponent</b> routines use activation reference counts to enable the various parts of the driver to independently maintain access to the component without requiring the driver to centrally manage access to the component.

PoFx maintains an activation reference count for each component in a device. A <b>PoFxActivateComponent</b> call increments this count by one, and a <b>PoFxIdleComponent</b> call decrements the count by one. When the count is nonzero, the component either is in the active condition or is in the process of switching to the active condition. A component that has a count of zero either is in the idle condition or is in the process of switching to the idle condition.

When a <b>PoFxActivateComponent</b> call causes the activation reference count to increment from 0 to 1, <b>PoFxActivateComponent</b> initiates a transition from the idle condition to the active condition. When a <b>PoFxIdleComponent</b> call causes the count to decrement from 1 to 0, <b>PoFxIdleComponent</b> initiates a transition from the active condition to the idle condition.

PoFx notifies the driver when a transition between the active condition and idle condition occurs. A <i>ComponentActiveConditionCallback</i> callback notifies the driver of a transition to the active condition, and a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_condition_callback">ComponentIdleConditionCallback</a> callback notifies the driver of a transition to the idle condition. When a <b>PoFxActivateComponent</b> or <b>PoFxIdleComponent</b> call simply increments or decrements the activation reference count without causing such a transition, the driver receives no notification.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_active_condition_callback">ComponentActiveConditionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_state_callback">ComponentIdleStateCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxidlecomponent">PoFxIdleComponent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a>

