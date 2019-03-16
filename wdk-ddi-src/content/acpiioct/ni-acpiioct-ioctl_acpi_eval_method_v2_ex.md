---
UID: NI:acpiioct.IOCTL_ACPI_EVAL_METHOD_V2_EX
title: IOCTL_ACPI_EVAL_METHOD_V2_EX (acpiioct.h)
description: The IOCTL_ACPI_EVAL_METHOD_V2_EX control code synchronously evaluates an ACPI control method that is supported by the device.
old-location: acpi\ioctl_acpi_eval_method_v2_ex.htm
tech.root: acpi
ms.assetid: 0BD23D27-D9B0-462D-A38A-BC96A089E60F
ms.date: 02/15/2018
ms.keywords: IOCTL_ACPI_EVAL_METHOD_V2_EX, IOCTL_ACPI_EVAL_METHOD_V2_EX control, IOCTL_ACPI_EVAL_METHOD_V2_EX control code [ACPI Devices], acpi.ioctl_acpi_eval_method_v2_ex, acpiioct/IOCTL_ACPI_EVAL_METHOD_V2_EX
ms.topic: ioctl
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Acpiioct.h
api_name:
- IOCTL_ACPI_EVAL_METHOD_V2_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_ACPI_EVAL_METHOD_V2_EX IOCTL


## -description


The <b>IOCTL_ACPI_EVAL_METHOD_V2_EX</b> control code synchronously evaluates an ACPI control method that is supported by the device.


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

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

