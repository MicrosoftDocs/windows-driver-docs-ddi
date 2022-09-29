---
UID: NE:pep_x._PEP_WORK_TYPE
title: _PEP_WORK_TYPE (pep_x.h)
description: Learn how the PEP_WORK_TYPE enumeration describes the type of work that the platform extension plug-in (PEP) is requesting.
old-location: kernel\pep_work_type.htm
tech.root: kernel
ms.date: 08/09/2022
keywords: ["PEP_WORK_TYPE enumeration"]
ms.keywords: "*PPEP_WORK_TYPE, PEP_WORK_TYPE, PEP_WORK_TYPE enumeration [Kernel-Mode Driver Architecture], PepWorkAcpiEvaluateControlMethodComplete, PepWorkAcpiNotify, PepWorkActiveComplete, PepWorkCompleteIdleState, PepWorkCompletePerfState, PepWorkDeviceIdle, PepWorkDevicePower, PepWorkMax, PepWorkRequestIdleState, PepWorkRequestPowerControl, _PEP_WORK_TYPE, kernel.pep_work_type, pepfx/PEP_WORK_TYPE, pepfx/PepWorkAcpiEvaluateControlMethodComplete, pepfx/PepWorkAcpiNotify, pepfx/PepWorkActiveComplete, pepfx/PepWorkCompleteIdleState, pepfx/PepWorkCompletePerfState, pepfx/PepWorkDeviceIdle, pepfx/PepWorkDevicePower, pepfx/PepWorkMax, pepfx/PepWorkRequestIdleState, pepfx/PepWorkRequestPowerControl"
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
targetos: Windows
req.typenames: PEP_WORK_TYPE, *PPEP_WORK_TYPE
f1_keywords:
 - _PEP_WORK_TYPE
 - pep_x/_PEP_WORK_TYPE
 - PPEP_WORK_TYPE
 - pep_x/PPEP_WORK_TYPE
 - PEP_WORK_TYPE
 - pep_x/PEP_WORK_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_WORK_TYPE
 - PPEP_WORK_TYPE
 - PEP_WORK_TYPE
---

# _PEP_WORK_TYPE enumeration (pep_x.h)

## -description

The **PEP_WORK_TYPE** enumeration describes the type of work that the platform extension plug-in (PEP) is requesting.

## -enum-fields

### -field PepWorkRequestPowerControl

A request for the device driver to perform a custom power-control operation that uses a device-specific context that the PEP provides for the operation. The driver handles this request in its [PowerControlCallback](../wdm/nc-wdm-po_fx_power_control_callback.md) routine.

### -field PepWorkCompleteIdleState

A notification to PoFx that the PEP has asynchronously completed the transition of a component to an idle state. PoFx previously initiated this transition by sending a [PEP_DPM_NOTIFY_COMPONENT_IDLE_STATE](../pepfx/ns-pepfx-_pep_notify_component_idle_state.md) notification to the PEP.

### -field PepWorkCompletePerfState

A notification to PoFx that the PEP has asynchronously completed the transition of a component to a P-state. PoFx previously initiated this transition by sending a [PEP_DPM_REQUEST_COMPONENT_PERF_STATE](../pepfx/ns-pepfx-_pep_request_component_perf_state.md) notification to the PEP.

### -field PepWorkAcpiNotify

An ACPI Notify code to describe to PoFx a hardware event that the specified device has generated.

### -field PepWorkAcpiEvaluateControlMethodComplete

A notification to PoFx that the PEP has asynchronously finished evaluating an ACPI control method. PoFx previously initiated the evaluation of this method by sending a [PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD](../pepfx/ns-pepfx-_pep_acpi_evaluate_control_method.md) notification to the PEP.

### -field PepWorkMax

Reserved for use by operating system.

## -remarks

This enumeration is used by the [PEP_WORK_INFORMATION](../pepfx/ns-pepfx-_pep_work_information.md) structure to describe the type of work item that the PEP is requesting.

## -see-also

- [PEP_DPM_NOTIFY_COMPONENT_IDLE_STATE](../pepfx/ns-pepfx-_pep_notify_component_idle_state.md)
- [PEP_DPM_REQUEST_COMPONENT_PERF_STATE](../pepfx/ns-pepfx-_pep_request_component_perf_state.md)
- [PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD](../pepfx/ns-pepfx-_pep_acpi_evaluate_control_method.md)
- [PEP_WORK_INFORMATION](../pepfx/ns-pepfx-_pep_work_information.md)
- [PowerControlCallback](../wdm/nc-wdm-po_fx_power_control_callback.md)
