---
UID: NE:pep_x._PEP_WORK_TYPE
title: _PEP_WORK_TYPE (pep_x.h)
description: The PEP_WORK_TYPE enumeration describes the type of work that the platform extension plug-in (PEP) is requesting.
old-location: kernel\pep_work_type.htm
tech.root: kernel
ms.assetid: 5AED6B9E-5DB8-44AF-925C-4B587D100040
ms.date: 04/30/2018
keywords: ["PEP_WORK_TYPE enumeration"]
ms.keywords: "*PPEP_WORK_TYPE, PEP_WORK_TYPE, PEP_WORK_TYPE enumeration [Kernel-Mode Driver Architecture], PepWorkAcpiEvaluateControlMethodComplete, PepWorkAcpiNotify, PepWorkActiveComplete, PepWorkCompleteIdleState, PepWorkCompletePerfState, PepWorkDeviceIdle, PepWorkDevicePower, PepWorkMax, PepWorkRequestIdleState, PepWorkRequestPowerControl, _PEP_WORK_TYPE, kernel.pep_work_type, pepfx/PEP_WORK_TYPE, pepfx/PepWorkAcpiEvaluateControlMethodComplete, pepfx/PepWorkAcpiNotify, pepfx/PepWorkActiveComplete, pepfx/PepWorkCompleteIdleState, pepfx/PepWorkCompletePerfState, pepfx/PepWorkDeviceIdle, pepfx/PepWorkDevicePower, pepfx/PepWorkMax, pepfx/PepWorkRequestIdleState, pepfx/PepWorkRequestPowerControl"
f1_keywords:
 - "pep_x/PEP_WORK_TYPE"
 - "PEP_WORK_TYPE"
req.header: pep_x.h
req.include-header: Pep_x.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_WORK_TYPE
targetos: Windows
req.typenames: PEP_WORK_TYPE, *PPEP_WORK_TYPE
---

# _PEP_WORK_TYPE enumeration


## -description


The <b>PEP_WORK_TYPE</b> enumeration describes the type of work that the platform extension plug-in (PEP) is requesting.


## -enum-fields




### -field PepWorkRequestPowerControl

A request for the device driver to perform a custom power-control operation that uses a device-specific context that the PEP provides for the operation. The driver handles this request in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_power_control_callback">PowerControlCallback</a> routine.


### -field PepWorkCompleteIdleState

A notification to PoFx that the PEP has asynchronously completed the transition of a component to an idle state. PoFx previously initiated this transition by sending a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_notify_component_idle_state">PEP_DPM_NOTIFY_COMPONENT_IDLE_STATE</a> notification to the PEP.


### -field PepWorkCompletePerfState

A notification to PoFx that the PEP has asynchronously completed the transition of a component to a P-state. PoFx previously initiated this transition by sending a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_request_component_perf_state">PEP_DPM_REQUEST_COMPONENT_PERF_STATE</a> notification to the PEP.


### -field PepWorkAcpiNotify

An ACPI Notify code to describe to PoFx a hardware event that the specified device has generated.


### -field PepWorkAcpiEvaluateControlMethodComplete

A notification to PoFx that the PEP has asynchronously finished evaluating an ACPI control method. PoFx previously initiated the evaluation of this method by sending a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_evaluate_control_method">PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD</a> notification to the PEP.


### -field PepWorkMax

Reserved for use by operating system.


#### - PepWorkActiveComplete

Reserved for use by the operating system.


#### - PepWorkDeviceIdle

A request for the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) either to start ignoring idle time-outs for the specified device, or to start monitoring these time-outs.


#### - PepWorkDevicePower

Reserved for use by the operating system.


#### - PepWorkRequestIdleState

Reserved for use by the operating system.


## -remarks



This enumeration is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a> structure to describe the type of work item that the PEP is requesting.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_notify_component_idle_state">PEP_DPM_NOTIFY_COMPONENT_IDLE_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_request_component_perf_state">PEP_DPM_REQUEST_COMPONENT_PERF_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_evaluate_control_method">PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_power_control_callback">PowerControlCallback</a>
 

 

