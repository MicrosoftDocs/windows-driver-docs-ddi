---
UID: NI:gnssdriver.IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
title: IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT (gnssdriver.h)
description: The IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT control code is used to request alert information from GNSS_BREADCRUMBING_ALERT_DATA when the breadcrumbing buffer has reached a level at which OS read operations should be performed.
old-location: gnss\ioctl_gnss_listen_breadcrumbing_alert_.htm
tech.root: gnss
ms.date: 02/15/2018
keywords: ["IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT IOCTL"]
ms.keywords: IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT, IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT control, IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT control code [Sensor Devices], gnss.ioctl_gnss_listen_breadcrumbing_alert_, gnssdriver/IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
req.header: gnssdriver.h
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
 - IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
 - gnssdriver/IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
---

# IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT IOCTL


## -description

The **IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT** control code is used to request alert information from [GNSS_BREADCRUMBING_ALERT_DATA](./ns-gnssdriver-gnss_breadcrumbing_alert_data.md) when the breadcrumbing buffer has reached a level at which OS read operations should be performed.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

Pointer to the input buffer.

### -input-buffer-length

Size of the input buffer.

### -output-buffer

Pointer to the output buffer.

### -output-buffer-length

Size of the output buffer.

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) code.

## -remarks

**IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT** is defined as follows in the gnssdriver.h header file:

```cpp
#define IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT \
    CTL_CODE( FILE_DEVICE_UNKNOWN, 0x072, METHOD_BUFFERED, FILE_ANY_ACCESS )
```

## -see-also

[Creating IOCTL Requests in Drivers](/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers)

[WdfIoTargetSendInternalIoctlOthersSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md)

[WdfIoTargetSendInternalIoctlSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md)

[WdfIoTargetSendIoctlSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md)
