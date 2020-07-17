---
UID: NI:gnssdriver.IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
title: IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT (gnssdriver.h)
description: The IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT control code is used to request alert information from GNSS_BREADCRUMBING_ALERT_DATA when the breadcrumbing buffer has reached a level at which OS read operations should be performed.
old-location: gnss\ioctl_gnss_listen_breadcrumbing_alert_.htm
tech.root: gnss
ms.assetid: 14D396B1-5F55-4902-8986-BD4CC5B2ACC4
ms.date: 02/15/2018
keywords: ["IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT IOCTL"]
ms.keywords: IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT, IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT control, IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT control code [Sensor Devices], gnss.ioctl_gnss_listen_breadcrumbing_alert_, gnssdriver/IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
f1_keywords:
 - "gnssdriver/IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT"
 - "IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- gnssdriver.h
api_name:
- IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT IOCTL

## -description

The **IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT** control code is used to request alert information from [GNSS_BREADCRUMBING_ALERT_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_breadcrumbing_alert_data) when the breadcrumbing buffer has reached a level at which OS read operations should be performed.

## -ioctlparameters

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

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) code.

## -remarks

**IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT** is defined as follows in the gnssdriver.h header file:

```cpp
#define IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT \
    CTL_CODE( FILE_DEVICE_UNKNOWN, 0x072, METHOD_BUFFERED, FILE_ANY_ACCESS )
```

## -see-also

[Creating IOCTL Requests in Drivers](https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers)

[WdfIoTargetSendInternalIoctlOthersSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously)

[WdfIoTargetSendInternalIoctlSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously)

[WdfIoTargetSendIoctlSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously)
