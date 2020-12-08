---
UID: NI:acpiioct.IOCTL_ACPI_ASYNC_EVAL_METHOD_V1
title: IOCTL_ACPI_ASYNC_EVAL_METHOD_V1 (acpiioct.h)
description: The IOCTL_ACPI_ASYNC_EVAL_METHOD_V1 control code asynchronously evaluates an ACPI control method that is supported by the device.
old-location: acpi\ioctl_acpi_async_eval_method_v1.htm
tech.root: acpi
ms.date: 02/15/2018
keywords: ["IOCTL_ACPI_ASYNC_EVAL_METHOD_V1 IOCTL"]
ms.keywords: IOCTL_ACPI_ASYNC_EVAL_METHOD_V1, IOCTL_ACPI_ASYNC_EVAL_METHOD_V1 control, IOCTL_ACPI_ASYNC_EVAL_METHOD_V1 control code [ACPI Devices], acpi.ioctl_acpi_async_eval_method_v1, acpiioct/IOCTL_ACPI_ASYNC_EVAL_METHOD_V1
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709 and later versions.
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
req.typenames: 
f1_keywords:
 - IOCTL_ACPI_ASYNC_EVAL_METHOD_V1
 - acpiioct/IOCTL_ACPI_ASYNC_EVAL_METHOD_V1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Acpiioct.h
api_name:
 - IOCTL_ACPI_ASYNC_EVAL_METHOD_V1
---

# IOCTL_ACPI_ASYNC_EVAL_METHOD_V1 IOCTL


## -description

The <b>IOCTL_ACPI_ASYNC_EVAL_METHOD_V1</b> control code asynchronously evaluates an ACPI control method that is supported by the device.

## -ioctlparameters

### -input-buffer

An input buffer structure that depends on the type of input arguments to be passed to the control method.

### -input-buffer-length

The size, in bytes, of the input buffer.

### -output-buffer

An output buffer structure that contains the output arguments from the control method.

### -output-buffer-length

The size, in bytes, of the output buffer.

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.

## -see-also

<a href="/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
