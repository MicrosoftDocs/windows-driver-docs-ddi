---
UID: NI:usbprint.IOCTL_USBPRINT_GET_LPT_STATUS
title: IOCTL_USBPRINT_GET_LPT_STATUS (usbprint.h)
description: The IOCTL_USBPRINT_GET_LPT_STATUS request allows upper-layer software (such as a language monitor), to request and obtain the printer status byte from a USB printer.
old-location: print\ioctl_usbprint_get_lpt_status.htm
tech.root: print
ms.assetid: 706e62f9-1be6-43bd-812a-dbb459877909
ms.date: 10/21/2020
keywords: ["IOCTL_USBPRINT_GET_LPT_STATUS IOCTL"]
ms.keywords: IOCTL_USBPRINT_GET_LPT_STATUS, IOCTL_USBPRINT_GET_LPT_STATUS control, IOCTL_USBPRINT_GET_LPT_STATUS control code [Print Devices], print.ioctl_usbprint_get_lpt_status, usbioctl_1729d0c7-8762-426e-bdb8-aa0bf38f71ee.xml, usbprint/IOCTL_USBPRINT_GET_LPT_STATUS
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
 - IOCTL_USBPRINT_GET_LPT_STATUS
 - usbprint/IOCTL_USBPRINT_GET_LPT_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbprint.h
api_name:
 - IOCTL_USBPRINT_GET_LPT_STATUS
---

# IOCTL_USBPRINT_GET_LPT_STATUS IOCTL

## -description

The **IOCTL_USBPRINT_GET_LPT_STATUS** request allows upper-layer software (such as a language monitor), to request and obtain the printer status byte from a USB printer.

## -ioctlparameters

### -input-buffer

Not used in this operation; set this parameter to **NULL**.

### -input-buffer-length

Not used in this operation; set this parameter to 0.

### -output-buffer

Pointer to a DWORD containing the printer status.

### -output-buffer-length

sizeof(DWORD)

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to **STATUS_SUCCESS** if the request is successful. Otherwise, **Status** to the appropriate error condition as an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) code.

## -see-also

[Creating IOCTL Requests in Drivers](/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers)

[WdfIoTargetSendInternalIoctlOthersSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md)

[WdfIoTargetSendInternalIoctlSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md)

[WdfIoTargetSendIoctlSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md)