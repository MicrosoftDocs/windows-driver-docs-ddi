---
UID: NS:pep_x._PEP_WORK_INFORMATION
title: _PEP_WORK_INFORMATION (pep_x.h)
description: The PEP_WORK_INFORMATION structure describes a work item that the PEP is submitting to the Windows power management framework (PoFx).
old-location: kernel\pep_work_information.htm
tech.root: kernel
ms.assetid: 7A3B2A94-AE6F-4DCC-9CDF-E2D5799C9F0D
ms.date: 04/30/2018
keywords: ["PEP_WORK_INFORMATION structure"]
ms.keywords: "*PPEP_WORK_INFORMATION, PEP_WORK_INFORMATION, PEP_WORK_INFORMATION structure [Kernel-Mode Driver Architecture], PPEP_WORK_INFORMATION, PPEP_WORK_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_INFORMATION, kernel.pep_work_information, pepfx/PEP_WORK_INFORMATION, pepfx/PPEP_WORK_INFORMATION"
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
req.typenames: PEP_WORK_INFORMATION, *PPEP_WORK_INFORMATION
f1_keywords:
 - _PEP_WORK_INFORMATION
 - pep_x/_PEP_WORK_INFORMATION
 - PPEP_WORK_INFORMATION
 - pep_x/PPEP_WORK_INFORMATION
 - PEP_WORK_INFORMATION
 - pep_x/PEP_WORK_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_WORK_INFORMATION
---

# _PEP_WORK_INFORMATION structure (pep_x.h)


## -description

The <b>PEP_WORK_INFORMATION</b> structure describes a work item that the PEP is submitting to the Windows <a href="/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">power management framework</a> (PoFx).

## -struct-fields

### -field WorkType

A <a href="/windows-hardware/drivers/ddi/pepfx/ne-pepfx-_pep_work_type">PEP_WORK_TYPE</a> enumeration value. This member indicates the type of work requested by the PEP, which also determines the type of structure that is contained in the unnamed union in the <b>PEP_WORK_INFORMATION</b> structure.

### -field PowerControl

### -field CompleteIdleState

### -field CompletePerfState

### -field AcpiNotify

### -field ControlMethodComplete

 




#### - ( unnamed union )

The data structure that is associated with the type of work specified by the <b>WorkType</b> member.



#### PowerControl

A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_power_control">PEP_WORK_POWER_CONTROL</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkRequestPowerControl</b>.



#### CompleteIdleState

A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_complete_idle_state">PEP_WORK_COMPLETE_IDLE_STATE</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkCompleteIdleState</b>.



#### CompletePerfState

A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_complete_perf_state">PEP_WORK_COMPLETE_PERF_STATE</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkCompletePerfState</b>.



#### AcpiNotify

A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_acpi_notify">PEP_WORK_ACPI_NOTIFY</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkAcpiNotify</b>.



#### ControlMethodComplete

A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_acpi_evaluate_control_method_complete">PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkAcpiEvaluateControlMethodComplete</b>.


##### - ( unnamed union ).AcpiNotify

A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_acpi_notify">PEP_WORK_ACPI_NOTIFY</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkAcpiNotify</b>.


##### - ( unnamed union ).CompleteIdleState

A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_complete_idle_state">PEP_WORK_COMPLETE_IDLE_STATE</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkCompleteIdleState</b>.


##### - ( unnamed union ).CompletePerfState

A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_complete_perf_state">PEP_WORK_COMPLETE_PERF_STATE</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkCompletePerfState</b>.


##### - ( unnamed union ).ControlMethodComplete

A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_acpi_evaluate_control_method_complete">PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkAcpiEvaluateControlMethodComplete</b>.


##### - ( unnamed union ).PowerControl

A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_power_control">PEP_WORK_POWER_CONTROL</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkRequestPowerControl</b>.

## -remarks

The <b>WorkInformation</b> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work">PEP_WORK</a> structure is a pointer to a <b>PEP_WORK_INFORMATION</b> structure.

## -see-also

<a href="/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work">PEP_WORK</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_acpi_notify">PEP_WORK_ACPI_NOTIFY</a>



<a href="/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_work_active_complete">PEP_WORK_ACTIVE_COMPLETE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_complete_idle_state">PEP_WORK_COMPLETE_IDLE_STATE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_complete_perf_state">PEP_WORK_COMPLETE_PERF_STATE</a>



<a href="/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_work_device_idle">PEP_WORK_DEVICE_IDLE</a>



<a href="/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_work_device_power">PEP_WORK_DEVICE_POWER</a>



<a href="/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_work_idle_state">PEP_WORK_IDLE_STATE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_power_control">PEP_WORK_POWER_CONTROL</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ne-pepfx-_pep_work_type">PEP_WORK_TYPE</a>