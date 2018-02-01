---
UID: NC:wdm.PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK
title: PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK
author: windows-driver-content
description: The ComponentActiveConditionCallback callback routine notifies the driver that the specified component completed a transition from the idle condition to the active condition.
old-location: kernel\componentactiveconditioncallback.htm
old-project: kernel
ms.assetid: D9EA3F98-7646-4882-BE07-818280404D6A
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.componentactiveconditioncallback, ComponentActiveConditionCallback routine [Kernel-Mode Driver Architecture], ComponentActiveConditionCallback, PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK, PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK, wdm/ComponentActiveConditionCallback
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
-	ComponentActiveConditionCallback
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK callback


## -description


The <i>ComponentActiveConditionCallback</i> callback routine notifies the driver that the specified component completed a transition from the idle condition to the active condition.


## -prototype


````
PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK ComponentActiveConditionCallback;

VOID ComponentActiveConditionCallback(
  _In_ PVOID Context,
  _In_ ULONG Component
)
{ ... }
````


## -parameters




### -param Context [in]

A pointer to the device context. The device driver uses this context to store information about the current power state of the device. The device driver specified this pointer in the <b>DeviceContext</b> member of the <a href="..\wdm\ns-wdm-_po_fx_device_v1.md">PO_FX_DEVICE</a> structure that the driver used to register the device with the power management framework (PoFx). This context is opaque to PoFx.


### -param Component [in]

Specifies the index that identifies the component. This parameter is an index into the <b>Components</b> array in the <b>PO_FX_DEVICE</b> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


## -returns


None.



## -remarks


A component's hardware registers can be accessed only when the component is in the active condition. Do not rely on the Fx power state of a component to determine whether the component can be accessed. If the component is in the F0 state and is in the idle condition, the component might be about to switch to another Fx state.

To gain access to a component that is in the idle condition, the driver can call the <a href="..\wdm\nf-wdm-pofxactivatecomponent.md">PoFxActivateComponent</a> routine to switch the component to the active condition. If the component is not already in the active condition when <b>PoFxActivateComponent</b> is called, PoFx initiates the transition to the active condition, and then calls the <i>ComponentActiveConditionCallback</i> routine to notify the driver when the transition is complete.

The driver receives a <i>ComponentActiveConditionCallback</i> callback whenever the component completes a transition to the active condition, regardless of whether the driver called <b>PoFxActivateComponent</b> to initiate the transition. For example, the Windows kernel might activate the component on behalf of the driver before sending a <a href="https://msdn.microsoft.com/339ef4b4-1b4f-42ac-ab57-c53b83120f0d">Plug and Play IRP</a> or a <a href="https://msdn.microsoft.com/a37e8dda-af7a-4f28-bf04-908a74bb5b2f">system set-power IRP</a> to the driver.



## -see-also

<a href="..\wdm\nf-wdm-pofxactivatecomponent.md">PoFxActivateComponent</a>

<a href="..\wdm\ns-wdm-_po_fx_device_v1.md">PO_FX_DEVICE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ComponentActiveConditionCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

