---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE
title: IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE (pointofservicedriverinterface.h)
description: This I/O control function is used to keep a claim on a device when a client is notified that its claim on the device is being contested by another client.
old-location: pos\ioctl_point_of_service_retain_device.htm
tech.root: pos
ms.assetid: c221862f-99db-4815-812f-8b22b46fff4a
ms.date: 08/21/2020
keywords: ["IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE, IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE control, IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE, pos.ioctl_point_of_service_retain_device
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
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
 - IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE
 - pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicedriverinterface.h
api_name:
 - IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE
---

# IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE IOCTL


## -description

This I/O control function is used to keep a claim on a device when a client is notified that its claim on the device is being contested by another client.

## -ioctlparameters

### -input-buffer

Not used with this operation; set to **NULL**.

### -input-buffer-length

Not used with this operation; set to **0** (zero).

### -output-buffer

Not used with this operation; set to **NULL**.

### -output-buffer-length

Not used with this operation; set to **0** (zero)

### -in-out-buffer

### -inout-buffer-length

### -status-block

Returns **TRUE** if successful; otherwise, returns **FALSE**.

## -remarks

To get extended error information, call [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). The following list shows common error values:

- STATUS_ACCESS_DENIED: The device is currently claimed by another client.

- STATUS_DEVICE_NOT_READY: The POS library has not successfully initialized.

This IOCTL only works if the client has previously called [IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE](./ni-pointofservicedriverinterface-ioctl_point_of_service_claim_device.md).

When handling this IOCTL, the driver can call [PosCxRetainDevice](../poscx/nf-poscx-poscxretaindevice.md). The driver writer does not need to handle claim contention because the PosCx library determines who gets the claim.