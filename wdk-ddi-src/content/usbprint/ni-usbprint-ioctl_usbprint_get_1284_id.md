---
UID: NI:usbprint.IOCTL_USBPRINT_GET_1284_ID
title: IOCTL_USBPRINT_GET_1284_ID (usbprint.h)
description: The IOCTL_USBPRINT_GET_1284_ID control code allows upper-layer software (such as a language monitor), to request and obtain the printer's IEEE 1284 device ID string.
old-location: print\ioctl_usbprint_get_1284_id.htm
tech.root: print
ms.assetid: b5c5a0e4-0fd9-4950-ac38-4bf58a0af077
ms.date: 02/26/2020
ms.keywords: IOCTL_USBPRINT_GET_1284_ID, IOCTL_USBPRINT_GET_1284_ID control, IOCTL_USBPRINT_GET_1284_ID control code [Print Devices], print.ioctl_usbprint_get_1284_id, usbioctl_4b1e9092-6483-4603-b690-a5e655a73670.xml, usbprint/IOCTL_USBPRINT_GET_1284_ID
f1_keywords:
 - "usbprint/IOCTL_USBPRINT_GET_1284_ID"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbprint.h
api_name:
- IOCTL_USBPRINT_GET_1284_ID
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USBPRINT_GET_1284_ID IOCTL

## -description

The **IOCTL_USBPRINT_GET_1284_ID** control code allows upper-layer software (such as a language monitor), to request and obtain the printer's IEEE 1284 device ID string.

## -ioctlparameters

### -input-buffer

Not used in this operation; set this parameter to **NULL**.

### -input-buffer-length

Not used in this operation; set this parameter to 0.

### -output-buffer

The output buffer will contain UCHAR data. On success this buffer can hold the following: a two-byte prefix that specifies the size, in bytes, of the device's IEEE 1284 device ID; the device ID; and a null terminator. An IEEE 1284 device ID can be up to 64 KB in size. On failure, if **GetLastError** returns the error code **STATUS_BUFFER_TOO_SMALL**, the output buffer was not large enough to hold the data intended for it.

### -output-buffer-length

The output buffer must be large enough to contain a two-byte quantity holding the length of the device's IEEE 1284 device ID, the device ID (up to 64 KB in size), and a terminating null.

> [!NOTE]
> The IOCTL_USBPRINT_GET_1284_ID output buffer length is placed directly into the USB packet. On some USB print devices, using the maximum 65535 bytes can cause the call to fail with error 23. Reduce the buffer to 4094 bytes or less to resolve this issue.

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to **STATUS_SUCCESS** if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) code.

## -see-also

[Creating IOCTL Requests in Drivers](https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers)

[WdfIoTargetSendInternalIoctlOthersSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously)

[WdfIoTargetSendInternalIoctlSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously)

[WdfIoTargetSendIoctlSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously)
