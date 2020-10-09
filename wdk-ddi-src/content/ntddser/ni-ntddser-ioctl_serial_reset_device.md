---
UID: NI:ntddser.IOCTL_SERIAL_RESET_DEVICE
title: IOCTL_SERIAL_RESET_DEVICE (ntddser.h)
description: The IOCTL_SERIAL_RESET_DEVICE request resets a serial device.
old-location: serports\ioctl_serial_reset_device.htm
tech.root: serports
ms.assetid: af7482b4-4622-40b7-af7a-c952813e7095
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_RESET_DEVICE IOCTL"]
ms.keywords: IOCTL_SERIAL_RESET_DEVICE, IOCTL_SERIAL_RESET_DEVICE control, IOCTL_SERIAL_RESET_DEVICE control code [Serial Ports], ntddser/IOCTL_SERIAL_RESET_DEVICE, serports.ioctl_serial_reset_device, serref_8c489e42-94d9-4a10-9336-dae4adea904a.xml
req.header: ntddser.h
req.include-header: Ntddser.h
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
 - IOCTL_SERIAL_RESET_DEVICE
 - ntddser/IOCTL_SERIAL_RESET_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - IOCTL_SERIAL_RESET_DEVICE
---

# IOCTL_SERIAL_RESET_DEVICE IOCTL


## -description

The <b>IOCTL_SERIAL_RESET_DEVICE</b> request resets a serial device.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.