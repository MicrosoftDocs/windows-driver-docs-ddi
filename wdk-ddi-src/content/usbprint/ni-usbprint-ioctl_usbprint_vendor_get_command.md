---
UID: NI:usbprint.IOCTL_USBPRINT_VENDOR_GET_COMMAND
title: IOCTL_USBPRINT_VENDOR_GET_COMMAND (usbprint.h)
description: The IOCTL_USBPRINT_VENDOR_GET_COMMAND request allows upper-layer software (such as a language monitor), to issue a vendor-specific GET command to the target device.
tech.root: print
ms.date: 03/08/2023
keywords: ["IOCTL_USBPRINT_VENDOR_GET_COMMAND IOCTL"]
ms.keywords: IOCTL_USBPRINT_VENDOR_GET_COMMAND, IOCTL_USBPRINT_VENDOR_GET_COMMAND control, IOCTL_USBPRINT_VENDOR_GET_COMMAND control code [Print Devices], print.ioctl_usbprint_vendor_get_command, usbioctl_edd39494-a6bb-4e28-a059-7c7884626105.xml, usbprint/IOCTL_USBPRINT_VENDOR_GET_COMMAND
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
 - IOCTL_USBPRINT_VENDOR_GET_COMMAND
 - usbprint/IOCTL_USBPRINT_VENDOR_GET_COMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbprint.h
api_name:
 - IOCTL_USBPRINT_VENDOR_GET_COMMAND
---

## -description

The **IOCTL_USBPRINT_VENDOR_GET_COMMAND** request allows upper-layer software (such as a language monitor), to issue a vendor-specific GET command to the target device.

## -ioctlparameters

### -input-buffer

A pointer to a buffer, an array of UCHAR elements. The meaning of each array element is shown in the following table.

| Array Element | Contents |
|---|---|
| *lpOutBuffer*\[0\] | Vendor request code |
| *lpOutBuffer*\[1\] | Vendor request value (most significant byte) |
| *lpOutBuffer*\[2\] | Vendor request value (least significant byte) |

### -input-buffer-length

The size of the input buffer, in bytes.

### -output-buffer

The output buffer, which is interpreted as an array of bytes.

### -output-buffer-length

The size of the output buffer, in bytes.

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to **STATUS_SUCCESS** if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) code.

## -see-also

[Creating IOCTL Requests in Drivers](/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers)

[IOCTL_USBPRINT_VENDOR_SET_COMMAND](./ni-usbprint-ioctl_usbprint_vendor_set_command.md)

[WdfIoTargetSendInternalIoctlOthersSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md)

[WdfIoTargetSendInternalIoctlSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md)

[WdfIoTargetSendIoctlSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md)