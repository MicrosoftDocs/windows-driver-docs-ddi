---
UID: NI:usbprint.IOCTL_USBPRINT_SOFT_RESET
title: IOCTL_USBPRINT_SOFT_RESET (usbprint.h)
description: The IOCTL_USBPRINT_SOFT_RESET request allows upper-layer software (such as a language monitor), to issue a class-specific soft reset command to the printer.
old-location: print\ioctl_usbprint_soft_reset.htm
tech.root: print
ms.assetid: 84e9197a-a096-42ff-af0d-3f4dab9fe0c6
ms.date: 04/20/2018
keywords: ["IOCTL_USBPRINT_SOFT_RESET IOCTL"]
ms.keywords: IOCTL_USBPRINT_SOFT_RESET, IOCTL_USBPRINT_SOFT_RESET control, IOCTL_USBPRINT_SOFT_RESET control code [Print Devices], print.ioctl_usbprint_soft_reset, usbioctl_282627ce-49eb-4d8c-88a6-8d211cb91830.xml, usbprint/IOCTL_USBPRINT_SOFT_RESET
req.header: usbprint.h
req.include-header: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_USBPRINT_SOFT_RESET
 - usbprint/IOCTL_USBPRINT_SOFT_RESET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbprint.h
api_name:
 - IOCTL_USBPRINT_SOFT_RESET
---

# IOCTL_USBPRINT_SOFT_RESET IOCTL


## -description

The <b>IOCTL_USBPRINT_SOFT_RESET</b> request allows upper-layer software (such as a language monitor), to issue a class-specific soft reset command to the printer.

## -ioctlparameters

### -input-buffer

Not used with this operation; set this parameter to <b>NULL</b>.

### -input-buffer-length

Not used with this operation; set this parameter to 0.

### -output-buffer

Not used with this operation; set this parameter to <b>NULL</b>.

### -output-buffer-length

Not used with this operation; set this parameter to 0.

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>

