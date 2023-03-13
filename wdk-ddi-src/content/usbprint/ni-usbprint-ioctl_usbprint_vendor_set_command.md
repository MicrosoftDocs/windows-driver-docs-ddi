---
UID: NI:usbprint.IOCTL_USBPRINT_VENDOR_SET_COMMAND
title: IOCTL_USBPRINT_VENDOR_SET_COMMAND (usbprint.h)
description: The IOCTL_USBPRINT_VENDOR_SET_COMMAND request allows upper-layer software (such as a language monitor) to issue a vendor-specific SET command to the target device.
tech.root: print
ms.date: 03/08/2023
keywords: ["IOCTL_USBPRINT_VENDOR_SET_COMMAND IOCTL"]
ms.keywords: IOCTL_USBPRINT_VENDOR_SET_COMMAND, IOCTL_USBPRINT_VENDOR_SET_COMMAND control, IOCTL_USBPRINT_VENDOR_SET_COMMAND control code [Print Devices], print.ioctl_usbprint_vendor_set_command, usbioctl_b3ea3ada-47c2-4acc-b08c-2d16e9d3ead1.xml, usbprint/IOCTL_USBPRINT_VENDOR_SET_COMMAND
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
 - IOCTL_USBPRINT_VENDOR_SET_COMMAND
 - usbprint/IOCTL_USBPRINT_VENDOR_SET_COMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbprint.h
api_name:
 - IOCTL_USBPRINT_VENDOR_SET_COMMAND
---

## -description

The **IOCTL_USBPRINT_VENDOR_SET_COMMAND** request allows upper-layer software (such as a language monitor) to issue a vendor-specific SET command to the target device.

## -ioctlparameters

### -input-buffer

A pointer to a input buffer, an array of UCHAR elements. The meaning of each array element is shown in the following table.

| Array Element | Contents |
|---|---|
| *lpInBuffer*\[0\] | Vendor request code |
| *lpInBuffer*\[1\] | Vendor request value (most significant byte) |
| *lpInBuffer*\[2\] | Vendor request value (least significant byte) |
| *lpInBuffer*\[3\], ... | Any additional data to be sent as part of the command |

### -input-buffer-length

The size of the input buffer, in bytes.

### -output-buffer

Not used in this operation; set this parameter to **NULL**.

### -output-buffer-length

Not used in this operation; set this parameter to 0.

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to **STATUS_SUCCESS** if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) code.

## -see-also

[Creating IOCTL Requests in Drivers](/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers)

[IOCTL_USBPRINT_VENDOR_GET_COMMAND](/windows-hardware/drivers/ddi/usbprint/ni-usbprint-ioctl_usbprint_vendor_get_command)

[WdfIoTargetSendInternalIoctlOthersSynchronously](/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously)

[WdfIoTargetSendInternalIoctlSynchronously](/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously)

[WdfIoTargetSendIoctlSynchronously](/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously)
