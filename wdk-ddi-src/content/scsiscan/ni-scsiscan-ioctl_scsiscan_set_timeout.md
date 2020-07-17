---
UID: NI:scsiscan.IOCTL_SCSISCAN_SET_TIMEOUT
title: IOCTL_SCSISCAN_SET_TIMEOUT (scsiscan.h)
description: The IOCTL_SCSISCAN_SET_TIMEOUT control code modifies the time-out value used by the kernel-mode still image driver for SCSI buses when it accesses a device.
old-location: image\ioctl_scsiscan_set_timeout.htm
tech.root: image
ms.assetid: 987816b3-ea5f-4689-b81f-f6d3328516c4
ms.date: 05/03/2018
keywords: ["IOCTL_SCSISCAN_SET_TIMEOUT IOCTL"]
ms.keywords: IOCTL_SCSISCAN_SET_TIMEOUT, IOCTL_SCSISCAN_SET_TIMEOUT control, IOCTL_SCSISCAN_SET_TIMEOUT control code [Imaging Devices], image.ioctl_scsiscan_set_timeout, scsiscan/IOCTL_SCSISCAN_SET_TIMEOUT, stifnc_2b449c8c-c9b5-4f5a-be93-7efc1d8610bc.xml
f1_keywords:
 - "scsiscan/IOCTL_SCSISCAN_SET_TIMEOUT"
 - "IOCTL_SCSISCAN_SET_TIMEOUT"
req.header: scsiscan.h
req.include-header: Scsiscan.h
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
- scsiscan.h
api_name:
- IOCTL_SCSISCAN_SET_TIMEOUT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SCSISCAN_SET_TIMEOUT IOCTL

## -description

The **IOCTL_SCSISCAN_SET_TIMEOUT** control code modifies the time-out value used by the kernel-mode still image driver for SCSI buses when it accesses a device.

## -ioctlparameters

### -input-buffer

The location containing a time-out value, in half seconds.

### -input-buffer-length

Size of the input buffer

### -output-buffer

Set to NULL.

### -output-buffer-length

Set to 0.

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) code.

## -remarks

When the kernel-mode SCSI still image driver sends a SCSI command to a device, by default the driver waits 30 seconds before timing out the operation. You can change the time-out value for a device by calling the **DeviceloControl** function with the [IOCTL_SCSISCAN_CMD](https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiscan/ni-scsiscan-ioctl_scsiscan_cmd) control code. The specified time-out value stays in effect until the device is closed.

Time-out values are specified in half seconds. Thus a specified value of 100 causes the driver to wait 50 seconds before timing out the device.

For more information, see [Accessing Kernel-Mode Drivers for Still Image Devices](https://docs.microsoft.com/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices).

### Code example

```cpp
ULONG timeout = 240;
fRet = DeviceIoControl( m_DeviceDataHandle,
        (DWORD)IOCTL_SCSISCAN_SET_TIMEOUT,
        &timeout,
        sizeof(ULONG),
        NULL, NULL, &dwBytesReturned, NULL);
```

## -see-also

[Creating IOCTL Requests in Drivers](https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers)

[WdfIoTargetSendInternalIoctlOthersSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously)

[WdfIoTargetSendInternalIoctlSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously)

[WdfIoTargetSendIoctlSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously)
