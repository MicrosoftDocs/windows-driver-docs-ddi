---
UID: NS:pepfx._PEP_WORK_INFORMATION
title: _PEP_WORK_INFORMATION (pepfx.h)
description: The PEP_WORK_INFORMATION structure describes a work item that the PEP is submitting to the Windows power management framework (PoFx).
old-location: kernel\pep_work_information.htm
tech.root: kernel
ms.date: 08/10/2022
keywords: ["PEP_WORK_INFORMATION structure"]
ms.keywords: "*PPEP_WORK_INFORMATION, PEP_WORK_INFORMATION, PEP_WORK_INFORMATION structure [Kernel-Mode Driver Architecture], PPEP_WORK_INFORMATION, PPEP_WORK_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_INFORMATION, kernel.pep_work_information, pepfx/PEP_WORK_INFORMATION, pepfx/PPEP_WORK_INFORMATION"
req.header: pepfx.h
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
req.typenames: PEP_WORK_INFORMATION, *PPEP_WORK_INFORMATION
f1_keywords:
 - _PEP_WORK_INFORMATION
 - pepfx/_PEP_WORK_INFORMATION
 - PPEP_WORK_INFORMATION
 - pepfx/PPEP_WORK_INFORMATION
 - PEP_WORK_INFORMATION
 - pepfx/PEP_WORK_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_WORK_INFORMATION
 - PPEP_WORK_INFORMATION
 - PEP_WORK_INFORMATION
---

# _PEP_WORK_INFORMATION structure (pepfx.h)

## -description

The **PEP_WORK_INFORMATION** structure describes a work item that the PEP is submitting to the Windows [power management framework](../_kernel/index.md#device-power-management) (PoFx).

## -struct-fields

### -field WorkType

A [PEP_WORK_TYPE](./ne-pepfx-_pep_work_type.md) enumeration value. This member indicates the type of work requested by the PEP, which also determines the type of structure that is contained in the unnamed union in the **PEP_WORK_INFORMATION** structure.

### -field PowerControl

A [PEP_WORK_POWER_CONTROL](./ns-pepfx-_pep_work_power_control.md) structure. This structure is used if `WorkType == PepWorkRequestPowerControl`.

### -field CompleteIdleState

A [PEP_WORK_COMPLETE_IDLE_STATE](./ns-pepfx-_pep_work_complete_idle_state.md) structure. This structure is used if `WorkType == PepWorkCompleteIdleState`.

### -field CompletePerfState

A [PEP_WORK_COMPLETE_PERF_STATE](./ns-pepfx-_pep_work_complete_perf_state.md) structure. This structure is used if `WorkType == PepWorkCompletePerfState`.

### -field AcpiNotify

A [PEP_WORK_ACPI_NOTIFY](./ns-pepfx-_pep_work_acpi_notify.md) structure. This structure is used if `WorkType == PepWorkAcpiNotify`.

### -field ControlMethodComplete

A [PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE](./ns-pepfx-_pep_work_acpi_evaluate_control_method_complete.md) structure. This structure is used if `WorkType == PepWorkAcpiEvaluateControlMethodComplete`.

## -remarks

The *WorkInformation* member of the [PEP_WORK](./ns-pepfx-_pep_work.md) structure is a pointer to a **PEP_WORK_INFORMATION** structure.

The unnamed union contains the data structure that is associated with the type of work specified by the *WorkType* member.

## -see-also

- [PEP_DPM_WORK](/windows-hardware/drivers/kernel/using-peps-for-acpi-services)
- [PEP_WORK](./ns-pepfx-_pep_work.md)
- [PEP_WORK_ACPI_NOTIFY](./ns-pepfx-_pep_work_acpi_notify.md)
- [PEP_WORK_ACTIVE_COMPLETE](../pep_x/ns-pep_x-_pep_work_active_complete.md)
- [PEP_WORK_COMPLETE_IDLE_STATE](./ns-pepfx-_pep_work_complete_idle_state.md)
- [PEP_WORK_COMPLETE_PERF_STATE](./ns-pepfx-_pep_work_complete_perf_state.md)
- [PEP_WORK_DEVICE_IDLE](../pep_x/ns-pep_x-_pep_work_device_idle.md)
- [PEP_WORK_DEVICE_POWER](../pep_x/ns-pep_x-_pep_work_device_power.md)
- [PEP_WORK_IDLE_STATE](../pep_x/ns-pep_x-_pep_work_idle_state.md)
- [PEP_WORK_POWER_CONTROL](./ns-pepfx-_pep_work_power_control.md)
- [PEP_WORK_TYPE](./ne-pepfx-_pep_work_type.md)
