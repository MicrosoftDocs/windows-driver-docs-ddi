---
UID: NS:pepfx._PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE
title: _PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE (pepfx.h)
description: The PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE structure contains the results of an ACPI control method that was asynchronously evaluated by the platform extension plug-in (PEP).
old-location: kernel\pep_work_acpi_evaluate_control_method_complete.htm
tech.root: kernel
ms.date: 07/29/2021
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
 - _PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE
 - PPEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE
 - PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE
---

# _PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE structure (pepfx.h)

## -description

The **PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE** structure contains the results of an ACPI control method that was asynchronously evaluated by the platform extension plug-in (PEP).

## -struct-fields

### -field DeviceHandle

A POHANDLE value that represents the registration of the device with the Windows [power management framework](/windows-hardware/drivers/ddi/_kernel/#device-power-management) (PoFx). The PEP previously received this handle from PoFx during the [PEP_NOTIFY_ACPI_REGISTER_DEVICE](/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device) notification in which the PEP elected to provide ACPI services for the device.

### -field CompletionFlags

A set of completion flags. No flags are currently defined for this member, which is always set to PEP_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE_FLAG_NONE (0x0).

### -field MethodStatus

### -field CompletionContext

A pointer to a completion context value. This is the same pointer that PoFx passed to the PEP in the [PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD](/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_evaluate_control_method) notification that initiated the asynchronous evaluation of the ACPI control method.

### -field OutputArgumentSize

The size, in bytes, of the buffer pointed to by the **OutputArguments** member.

### -field OutputArguments

A pointer to a buffer to which the PEP has written the result of evaluating the ACPI control method. This buffer starts with a [ACPI_METHOD_ARGUMENT](/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_method_argument_v1) structure, which might be followed by additional output data. PoFx allocated this buffer and passed the buffer pointer to the PEP in the [PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD](/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_evaluate_control_method) notification that initiated the asynchronous evaluation of the ACPI control method.

## -remarks

The **ControlMethodComplete** member of the [PEP_WORK_INFORMATION](/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information) structure is a **PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE** structure.

A **PEP_WORK_INFORMATION** structure is included in the input parameters to the *CompleteWork* routine. The PEP writes the control method results to the **ControlMethodComplete** member of this structure before calling the routine. Evaluation of the control method was initiated by a previous [PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD](/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_evaluate_control_method) notification.

## -see-also

[ACPI_METHOD_ARGUMENT](/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_method_argument_v1)

[PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD](/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_evaluate_control_method)

[PEP_NOTIFY_ACPI_REGISTER_DEVICE](/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device)

[PEP_WORK_INFORMATION](/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information)
