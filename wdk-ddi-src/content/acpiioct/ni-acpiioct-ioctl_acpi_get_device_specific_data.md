---
UID: NI:acpiioct.IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA
title: IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA (acpiioct.h)
description: The IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA control code is used to get device specific data.
old-location: acpi\ioctl_acpi_get_device_specific_data.htm
tech.root: acpi
ms.assetid: D77E272D-833E-40EA-97AA-137E0A219730
ms.date: 02/15/2018
keywords: ["IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA IOCTL"]
ms.keywords: IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA, IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA control, IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA control code [ACPI Devices], acpi.ioctl_acpi_get_device_specific_data, acpiioct/IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA
f1_keywords:
 - "acpiioct/IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA"
 - "IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA"
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA IOCTL


## -description


The <b>IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA</b> control code is used to get device specific data.




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

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

