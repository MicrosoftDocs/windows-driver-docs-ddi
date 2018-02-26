---
UID: NC:wudfwdm.PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK
title: PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK
author: windows-driver-content
description: The ComponentCriticalTransitionCallback callback routine handles a transition of the specified component between the F0 (fully on) and low-power Fx component power states.
old-location: kernel\componentcriticaltransitioncallback.htm
old-project: kernel
ms.assetid: 6E551951-E903-4970-8B30-6780C9FF4FC6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ComponentCriticalTransitionCallback, ComponentCriticalTransitionCallback routine [Kernel-Mode Driver Architecture], PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK, kernel.componentcriticaltransitioncallback, wdm/ComponentCriticalTransitionCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wudfwdm.h
req.include-header: Wudfwdm.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: TBD
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	ComponentCriticalTransitionCallback
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK callback


## -description


The <i>ComponentCriticalTransitionCallback</i> callback routine handles a transition of the specified component between the F0 (fully on) and low-power F<i>x</i> component power states.


## -prototype


````
PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK ComponentCriticalTransitionCallback;

VOID ComponentCriticalTransitionCallback(
  _In_ PVOID   Context,
  _In_ ULONG   Component,
  _In_ BOOLEAN Active
)
{ ... }
````


## -parameters




### -param Context [in]

A pointer to the device context. The device driver uses this context to store information about the current power state of the device. This context is driver-defined and is opaque to PoFx. The driver specified this pointer in the <b>DeviceContext</b> member of the <a href="..\pep_x\ns-pep_x-_po_fx_core_device.md">PO_FX_CORE_DEVICE</a> structure that the driver used to register the device with the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).


### -param Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <b>PO_FX_CORE_DEVICE</b> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -param Active [in]

Indicates whether this notification is for a transition to the F0 component power state. If TRUE, the component has just completed a transition from a low-power F<i>x</i> state to F0. If FALSE, the component is about to start a transition from F0 to a low-power F<i>x</i> state.


## -returns



None.




## -remarks



This callback routine is implemented by a device driver, and is called by PoFx. PoFx calls this routine to notify the driver of power transitions of device components.

The <b>ComponentCriticalTransitionCallback</b> member of the <a href="..\pep_x\ns-pep_x-_po_fx_core_device.md">PO_FX_CORE_DEVICE</a> structure is a pointer to a <i>ComponentCriticalTransitionCallback</i> callback routine. A pointer to a <b>PO_FX_CORE_DEVICE</b> structure is passed as an input parameter in the PoFxRegisterCoreDevice call that registers a core device with the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).

To handle calls to this routine, the device driver saves or restores the register state or other hardware context of the specified component in the device.

If <i>Active</i> = TRUE, PoFx has called this routine <i>after</i> the component completed a transition from a low-power F<i>x</i> state to F0. In this call, the routine restores the previously saved hardware context of the component.

If <i>Active</i> = FALSE, PoFx has called this routine <i>before</i> the component starts a pending transition from F0 to a low-power F<i>x</i> state. In this call, the routine saves the component's hardware context so that this context can later be restored.

For more information about F<i>x</i> component power states, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450935">Component-Level Power Management</a>.

A PEP can call this routine at IRQL TBD.




## -see-also

<a href="..\pep_x\ns-pep_x-_po_fx_core_device.md">PO_FX_CORE_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ComponentCriticalTransitionCallback routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

