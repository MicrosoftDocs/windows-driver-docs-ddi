---
UID: NI:ntddser.IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE
title: IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE
author: windows-driver-content
description: The IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE request disables the wait/wake operation of a serial device.
old-location: serports\ioctl_serial_internal_cancel_wait_wake.htm
old-project: serports
ms.assetid: 007701f4-4ee0-46e1-963c-e2af2a441a81
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SdBusSubmitRequestAsync
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE
req.alt-loc: ntddser.h
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
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE IOCTL



## -description

The IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE request disables the wait/wake operation of a serial device.



The IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE request disables the wait/wake operation of a serial device.



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

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="serial_device_control_requests.htm#generic_status_values_for_serial_device_control_requests">Generic Status Values for Serial Device Control Requests</a>.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl_serial_internal_do_wait_wake.md">IOCTL_SERIAL_INTERNAL_DO_WAIT_WAKE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

