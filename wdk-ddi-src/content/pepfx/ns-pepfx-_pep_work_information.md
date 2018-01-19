---
UID: NS:pepfx._PEP_WORK_INFORMATION
title: _PEP_WORK_INFORMATION
author: windows-driver-content
description: The PEP_WORK_INFORMATION structure describes a work item that the PEP is submitting to the Windows power management framework (PoFx).
old-location: kernel\pep_work_information.htm
old-project: kernel
ms.assetid: 7A3B2A94-AE6F-4DCC-9CDF-E2D5799C9F0D
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _PEP_WORK_INFORMATION, PEP_WORK_INFORMATION, *PPEP_WORK_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_WORK_INFORMATION
req.alt-loc: pepfx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: PEP_WORK_INFORMATION, *PPEP_WORK_INFORMATION
---

# _PEP_WORK_INFORMATION structure



## -description
The <b>PEP_WORK_INFORMATION</b> structure describes a work item that the PEP is submitting to the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx).



## -syntax

````
typedef struct _PEP_WORK_INFORMATION {
  PEP_WORK_TYPE WorkType;
  union {
    PEP_WORK_POWER_CONTROL                         PowerControl;
    PEP_WORK_COMPLETE_IDLE_STATE                   CompleteIdleState;
    PEP_WORK_COMPLETE_PERF_STATE                   CompletePerfState;
    PEP_WORK_ACPI_NOTIFY                           AcpiNotify;
    PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE ControlMethodComplete;
  };
} PEP_WORK_INFORMATION, *PPEP_WORK_INFORMATION;
````


## -struct-fields

### -field WorkType

A <a href="..\pepfx\ne-pepfx-_pep_work_type.md">PEP_WORK_TYPE</a> enumeration value. This member indicates the type of work requested by the PEP, which also determines the type of structure that is contained in the unnamed union in the <b>PEP_WORK_INFORMATION</b> structure.


### -field ( unnamed union )

The data structure that is associated with the type of work specified by the <b>WorkType</b> member.


### -field PowerControl

A <a href="..\pepfx\ns-pepfx-_pep_work_power_control.md">PEP_WORK_POWER_CONTROL</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkRequestPowerControl</b>.


### -field CompleteIdleState

A <a href="..\pepfx\ns-pepfx-_pep_work_complete_idle_state.md">PEP_WORK_COMPLETE_IDLE_STATE</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkCompleteIdleState</b>.


### -field CompletePerfState

A <a href="..\pepfx\ns-pepfx-_pep_work_complete_perf_state.md">PEP_WORK_COMPLETE_PERF_STATE</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkCompletePerfState</b>.


### -field AcpiNotify

A <a href="..\pepfx\ns-pepfx-_pep_work_acpi_notify.md">PEP_WORK_ACPI_NOTIFY</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkAcpiNotify</b>.


### -field ControlMethodComplete

A <a href="..\pepfx\ns-pepfx-_pep_work_acpi_evaluate_control_method_complete.md">PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkAcpiEvaluateControlMethodComplete</b>.

</dd>
</dl>

## -remarks
The <b>WorkInformation</b> member of the <a href="..\pepfx\ns-pepfx-_pep_work.md">PEP_WORK</a> structure is a pointer to a <b>PEP_WORK_INFORMATION</b> structure.


## -see-also
<dl>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_work.md">PEP_WORK</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_work_acpi_notify.md">PEP_WORK_ACPI_NOTIFY</a>
</dt>
<dt>
<a href="..\pep_x\ns-pep_x-_pep_work_active_complete.md">PEP_WORK_ACTIVE_COMPLETE</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_work_complete_idle_state.md">PEP_WORK_COMPLETE_IDLE_STATE</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_work_complete_perf_state.md">PEP_WORK_COMPLETE_PERF_STATE</a>
</dt>
<dt>
<a href="..\pep_x\ns-pep_x-_pep_work_device_idle.md">PEP_WORK_DEVICE_IDLE</a>
</dt>
<dt>
<a href="..\pep_x\ns-pep_x-_pep_work_device_power.md">PEP_WORK_DEVICE_POWER</a>
</dt>
<dt>
<a href="..\pep_x\ns-pep_x-_pep_work_idle_state.md">PEP_WORK_IDLE_STATE</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_work_power_control.md">PEP_WORK_POWER_CONTROL</a>
</dt>
<dt>
<a href="..\pepfx\ne-pepfx-_pep_work_type.md">PEP_WORK_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_WORK_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

