---
UID: NS:usbscan._USBSCAN_TIMEOUT
title: _USBSCAN_TIMEOUT (usbscan.h)
description: The USBSCAN_TIMEOUT structure stores time-out values for USB bulk IN and bulk OUT operations, and interrupts.
old-location: image\usbscan_timeout.htm
tech.root: image
ms.assetid: afa900fc-7297-425b-8308-18806d7d97d3
ms.date: 05/03/2018
keywords: ["USBSCAN_TIMEOUT structure"]
ms.keywords: "*PUSBSCAN_TIMEOUT, PUSBSCAN_TIMEOUT, PUSBSCAN_TIMEOUT structure pointer [Imaging Devices], USBSCAN_TIMEOUT, USBSCAN_TIMEOUT structure [Imaging Devices], _USBSCAN_TIMEOUT, image.usbscan_timeout, stifnc_ebdd7bda-2eb0-446c-a52c-e9a80f6478da.xml, usbscan/PUSBSCAN_TIMEOUT, usbscan/USBSCAN_TIMEOUT"
req.header: usbscan.h
req.include-header: Usbscan.h
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
req.typenames: USBSCAN_TIMEOUT, *PUSBSCAN_TIMEOUT
f1_keywords:
 - _USBSCAN_TIMEOUT
 - usbscan/_USBSCAN_TIMEOUT
 - PUSBSCAN_TIMEOUT
 - usbscan/PUSBSCAN_TIMEOUT
 - USBSCAN_TIMEOUT
 - usbscan/USBSCAN_TIMEOUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbscan.h
api_name:
 - USBSCAN_TIMEOUT
---

# _USBSCAN_TIMEOUT structure


## -description

The USBSCAN_TIMEOUT structure stores time-out values for USB bulk IN and bulk OUT operations, and interrupts.

## -struct-fields

### -field TimeoutRead

Specifies the number of seconds to wait for a read operation to time out.

### -field TimeoutWrite

Specifies the number of seconds to wait for a write operation to time out.

### -field TimeoutEvent

Specifies the number of seconds to wait for an interrupt to occur.

## -remarks

A value of zero means to wait forever for the read or write operation or interrupt.

The USBSCAN_TIMEOUT structure is used as a parameter to <a href="https://docs.microsoft.com/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>, when the specified I/O control code is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ni-usbscan-ioctl_set_timeout">IOCTL_SET_TIMEOUT</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ni-usbscan-ioctl_set_timeout">IOCTL_SET_TIMEOUT</a>

