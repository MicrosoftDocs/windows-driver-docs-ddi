---
UID: NC:wdm.PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK
title: PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK (wdm.h)
description: The ComponentIdleConditionCallback callback routine notifies the driver that the specified component completed a transition from the active condition to the idle condition.
old-location: kernel\componentidleconditioncallback.htm
tech.root: kernel
ms.assetid: 785DF693-DB7A-4675-9F33-200F17093333
ms.date: 04/30/2018
ms.keywords: ComponentIdleConditionCallback, ComponentIdleConditionCallback routine [Kernel-Mode Driver Architecture], PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK, kernel.componentidleconditioncallback, wdm/ComponentIdleConditionCallback
ms.topic: callback
req.header: wdm.h
req.include-header: Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- ComponentIdleConditionCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK callback function


## -description


The <i>ComponentIdleConditionCallback</i> callback routine notifies the driver that the specified component completed a transition from the active condition to the idle condition.


## -parameters




### -param Context [in]

A pointer to the device context. The device driver uses this context to store information about the current power state of the device. The device driver specified this pointer in the <b>DeviceContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a> structure that the driver used to register the device with the power management framework (PoFx). This context is opaque to PoFx.


### -param Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <b>PO_FX_DEVICE</b> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


## -returns



None.




## -remarks



When the driver no longer needs to access a component that is in the active condition, the driver should call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pofxidlecomponent">PoFxIdleComponent</a> routine to switch the component to the idle condition. In response to the <b>PoFxIdleComponent</b> call, PoFx initiates the transition to the idle condition, and then calls the <i>ComponentIdleConditionCallback</i> routine to notify the driver when this transition is complete.

The driver must call <b>PoFxCompleteIdleCondition</b> in response to every <i>ComponentIdleConditionCallback</i> callback. The <b>PoFxCompleteIdleCondition</b> call can occur either during the <i>ComponentIdleConditionCallback</i> callback or after the callback returns. The driver should complete any work that requires access to the hardware component before the call to <b>PoFxCompleteIdleCondition</b>. After this call, the component might not stay in the F0 power state.

A component can be safely accessed only when the component is in the active condition. Do not rely on the Fx power state of a component to determine whether the component can be accessed. If the component is in the F0 state and is in the idle condition, the component might be about to switch to another Fx state.


#### Examples

To define a <i>ComponentIdleConditionCallback</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ComponentIdleConditionCallback</i> callback routine that is named <code>MyComponentIdleConditionCallback</code>, use the PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK MyComponentIdleConditionCallback;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MyComponentIdleConditionCallback(
    PVOID Context,
    ULONG Component
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pofxcompleteidlecondition">PoFxCompleteIdleCondition</a>
 

 

