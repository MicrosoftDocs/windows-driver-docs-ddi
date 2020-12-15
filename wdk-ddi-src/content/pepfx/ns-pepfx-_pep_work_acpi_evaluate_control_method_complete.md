---
UID: NS:pepfx._PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE
title: _PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE (pepfx.h)
description: The PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE structure contains the results of an ACPI control method that was asynchronously evaluated by the platform extension plug-in (PEP).
old-location: kernel\pep_work_acpi_evaluate_control_method_complete.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE structure"]
ms.keywords: "*PPEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE, PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE, PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE structure [Kernel-Mode Driver Architecture], PPEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE, PPEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE, kernel.pep_work_acpi_evaluate_control_method_complete, pepfx/PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE, pepfx/PPEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE"
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
req.typenames: PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE, *PPEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE
f1_keywords:
 - _PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE
 - pepfx/_PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE
 - PPEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE
 - pepfx/PPEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE
 - PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE
 - pepfx/PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE
---

# _PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE structure (pepfx.h)


## -description

The <b>PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE</b> structure contains the results of an ACPI control method that was asynchronously evaluated by the platform extension plug-in (PEP).

## -struct-fields

### -field DeviceHandle

A POHANDLE value that represents the registration of the device with the Windows <a href="/windows-hardware/drivers/ddi/_kernel/#device-power-management">power management framework</a> (PoFx). The PEP previously received this handle from PoFx during the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification in which the PEP elected to provide ACPI services for the device.

### -field CompletionFlags

A set of completion flags. No flags are currently defined for this member, which is always set to PEP_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE_FLAG_NONE (0x0).

### -field MethodStatus

### -field CompletionContext

A pointer to a completion context value. This is the same pointer that PoFx passed to the PEP in the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_evaluate_control_method">PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD</a> notification that initiated the asynchronous evaluation of the ACPI control method.

### -field OutputArgumentSize

The size, in bytes, of the buffer pointed to by the <b>OutputArguments</b> member.

### -field OutputArguments

A pointer to a buffer to which the PEP has written the result of evaluating the ACPI control method. This buffer starts with a <a href="/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_method_argument_v1">ACPI_METHOD_ARGUMENT</a> structure, which might be followed by additional output data. PoFx allocated this buffer and passed the buffer pointer to the PEP in the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_evaluate_control_method">PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD</a> notification that initiated the asynchronous evaluation of the ACPI control method.

## -remarks

The <b>ControlMethodComplete</b> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a> structure is a <b>PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE</b> structure.

A <b>PEP_WORK_INFORMATION</b> structure is included in the input parameters to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186629">CompleteWork</a> routine. The PEP writes the control method results to the <b>ControlMethodComplete</b> member of this structure before calling the routine. Evaluation of the control method was initiated by a previous <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_evaluate_control_method">PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD</a> notification.

## -see-also

<a href="/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_method_argument_v1">ACPI_METHOD_ARGUMENT</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_evaluate_control_method">PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a>
