---
UID: NC:wdm.PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK
title: PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK
author: windows-driver-content
description: The ComponentIdleConditionCallback callback routine notifies the driver that the specified component completed a transition from the active condition to the idle condition.
old-location: kernel\componentidleconditioncallback.htm
old-project: kernel
ms.assetid: 785DF693-DB7A-4675-9F33-200F17093333
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.componentidleconditioncallback, ComponentIdleConditionCallback routine [Kernel-Mode Driver Architecture], ComponentIdleConditionCallback, PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK, PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK, wdm/ComponentIdleConditionCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	ComponentIdleConditionCallback
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK callback


## -description


The <i>ComponentIdleConditionCallback</i> callback routine notifies the driver that the specified component completed a transition from the active condition to the idle condition.


## -prototype


````
PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK ComponentIdleConditionCallback;

VOID ComponentIdleConditionCallback(
  _In_ PVOID Context,
  _In_ ULONG Component
)
{ ... }
````


## -parameters




### -param Context [in]

A pointer to the device context. The device driver uses this context to store information about the current power state of the device. The device driver specified this pointer in the <b>DeviceContext</b> member of the <a href="..\wdm\ns-wdm-_po_fx_device_v1.md">PO_FX_DEVICE</a> structure that the driver used to register the device with the power management framework (PoFx). This context is opaque to PoFx.


### -param Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <b>PO_FX_DEVICE</b> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


## -returns


None.



## -remarks


When the driver no longer needs to access a component that is in the active condition, the driver should call the <a href="..\wdm\nf-wdm-pofxidlecomponent.md">PoFxIdleComponent</a> routine to switch the component to the idle condition. In response to the <b>PoFxIdleComponent</b> call, PoFx initiates the transition to the idle condition, and then calls the <i>ComponentIdleConditionCallback</i> routine to notify the driver when this transition is complete.

The driver must call <b>PoFxCompleteIdleCondition</b> in response to every <i>ComponentIdleConditionCallback</i> callback. The <b>PoFxCompleteIdleCondition</b> call can occur either during the <i>ComponentIdleConditionCallback</i> callback or after the callback returns. The driver should complete any work that requires access to the hardware component before the call to <b>PoFxCompleteIdleCondition</b>. After this call, the component might not stay in the F0 power state.

A component can be safely accessed only when the component is in the active condition. Do not rely on the Fx power state of a component to determine whether the component can be accessed. If the component is in the F0 state and is in the idle condition, the component might be about to switch to another Fx state.



## -see-also

<a href="..\wdm\nf-wdm-pofxcompleteidlecondition.md">PoFxCompleteIdleCondition</a>

<a href="..\wdm\ns-wdm-_po_fx_device_v1.md">PO_FX_DEVICE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ComponentIdleConditionCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

