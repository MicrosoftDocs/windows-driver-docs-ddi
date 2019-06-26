---
UID: NF:wdm.PoFxSetComponentLatency
title: PoFxSetComponentLatency function (wdm.h)
description: The PoFxSetComponentLatency routine specifies the maximum latency that can be tolerated in the transition from the idle condition to the active condition in the specified component.
old-location: kernel\pofxsetcomponentlatency.htm
tech.root: kernel
ms.assetid: 670AFE37-1617-4171-9504-50B13B8E0F76
ms.date: 04/30/2018
ms.keywords: PoFxSetComponentLatency, PoFxSetComponentLatency routine [Kernel-Mode Driver Architecture], kernel.pofxsetcomponentlatency, wdm/PoFxSetComponentLatency
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Ntoskrnl.exe
api_name:
- PoFxSetComponentLatency
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoFxSetComponentLatency function


## -description


The <b>PoFxSetComponentLatency</b> routine specifies the maximum latency that can be tolerated in the transition from the idle condition to the active condition in the specified component.


## -parameters




### -param Handle [in]

A handle that represents the registration of the device with the power management framework (PoFx). The device driver previously received this handle from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> routine.


### -param Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -param Latency [in]

The maximum latency, in 100-nanosecond units, that can be tolerated in the specified component. For more information, see Remarks.


## -returns



None.




## -remarks



The calling driver supplies a maximum latency that clients of the device can tolerate in the specified component. This latency is the time required to complete a transition from the idle condition to the active condition. PoFx uses this latency as a hint to improve performance.

When the component switches from the active condition to the idle condition, PoFx selects an appropriate low-power Fx state for the component to enter. After this transition completes, the time required to switch back to the active condition depends on the selected Fx state. PoFx tries to select an Fx state that does not violate the maximum latency requirement.

For example, if a driver supports power states F0, F1, and F2 in the specified component, the F2 state represents a lower power setting than the F1 state. Typically, the time T2 required to wake (to the fully on state, F0) from F2 is longer than the time T1 required to wake from F1. If the maximum latency is greater than T1 but less than T2, PoFx can safely switch the component to the F1 state and still meet the maximum latency requirement. However, PoFx avoids switching the component to the F2 state because doing so violates this requirement.

The device driver can call <b>PoFxSetComponentLatency</b> each time a change in conditions requires a change in the maximum latency. After each call, the new maximum latency remains in effect until the driver calls <b>PoFxSetComponentLatency</b> again to update it.

If a component is in the idle condition when <b>PoFxSetComponentLatency</b> is called, PoFx might change the component’s current Fx state to accommodate the new maximum latency specified by the caller.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a>
 

 

