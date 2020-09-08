---
UID: NC:wdm.PO_FX_COMPONENT_PERF_STATE_CALLBACK
title: PO_FX_COMPONENT_PERF_STATE_CALLBACK (wdm.h)
description: The ComponentPerfStateCallback callback routine notifies the driver that its request to change the performance state of a component is complete.
old-location: kernel\componentperfstatecallback.htm
tech.root: kernel
ms.assetid: A54376E6-FBA2-4A27-83C7-8E3B6F2B2A05
ms.date: 04/30/2018
keywords: ["PO_FX_COMPONENT_PERF_STATE_CALLBACK callback function"]
ms.keywords: ComponentPerfStateCallback, ComponentPerfStateCallback routine [Kernel-Mode Driver Architecture], PO_FX_COMPONENT_PERF_STATE_CALLBACK, kernel.componentperfstatecallback, wdm/ComponentPerfStateCallback
req.header: wdm.h
req.include-header: 
req.target-type: Desktop
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - PO_FX_COMPONENT_PERF_STATE_CALLBACK
 - wdm/PO_FX_COMPONENT_PERF_STATE_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - ComponentPerfStateCallback
---

# PO_FX_COMPONENT_PERF_STATE_CALLBACK callback function


## -description

The <i>ComponentPerfStateCallback</i> callback routine notifies the driver that its request to change the performance state of a component is complete.

## -parameters

### -param Context 

[in]
A pointer to the device context. The device driver uses this context to store information about the current power state of the device. The device driver specified this pointer in the <b>DeviceContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a> structure that the driver used to register the device with the power management framework (PoFx). This context is opaque to PoFx.

### -param Component 

[in]
Specifies the index that identifies the component. This parameter is an index into the <b>Components</b> array in the <b>PO_FX_DEVICE</b> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

### -param Succeeded 

[in]
If TRUE, the platform extension plug-in (PEP) succeeded the performance state change. If FALSE, the PEP failed the performance state change. For more information, see the Remarks section.

### -param RequestContext 

[in]
Pointer to the optional driver or device context that was specified by the <i>Context</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxissuecomponentperfstatechange">PoFxIssueComponentPerfStateChange</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxissuecomponentperfstatechangemultiple">PoFxIssueComponentPerfStateChangeMultiple</a> routine.

## -remarks

When a device driver requests a performance state change by calling the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxissuecomponentperfstatechange">PoFxIssueComponentPerfStateChange</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxissuecomponentperfstatechangemultiple">PoFxIssueComponentPerfStateChangeMultiple</a> routine, PoFx calls the <i>ComponentPerfStateCallback</i>  routine to notify the driver when the request is complete. 

To specify a <i>ComponentPerfStateCallback</i> routine, use the <i>ComponentPerfStateCallback</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregistercomponentperfstates">PoFxRegisterComponentPerfStates</a> routine when the driver registers for performance state management by PoFx. The <i>ComponentPerfStateCallback</i> routine may be the same for all components and all devices.

If <i>Succeeded</i> is TRUE, the driver should perform whatever work is necessary to change the performance state in the hardware. If <i>Succeeded</i> is FALSE, the driver may choose to do nothing or retry the request with the same performance state or an alternate performance state.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxissuecomponentperfstatechange">PoFxIssueComponentPerfStateChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxissuecomponentperfstatechangemultiple">PoFxIssueComponentPerfStateChangeMultiple</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a>

