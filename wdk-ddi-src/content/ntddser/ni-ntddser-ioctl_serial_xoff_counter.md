---
UID: NI:ntddser.IOCTL_SERIAL_XOFF_COUNTER
title: IOCTL_SERIAL_XOFF_COUNTER
author: windows-driver-content
description: The IOCTL_SERIAL_XOFF_COUNTER request sets an XOFF counter. An XOFF counter request supports clients that use software to emulate hardware handshake flow control.
old-location: serports\ioctl_serial_xoff_counter.htm
old-project: serports
ms.assetid: c24451cd-87d7-493d-83cb-2ee96590b8a3
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
req.alt-api: IOCTL_SERIAL_XOFF_COUNTER
req.alt-loc: Ntddser.h
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

# IOCTL_SERIAL_XOFF_COUNTER IOCTL



## -description
The <b>IOCTL_SERIAL_XOFF_COUNTER</b> request sets an <i>XOFF counter</i>. An XOFF counter request supports clients that use software to emulate hardware handshake flow control.

An XOFF counter request is synchronized with write requests. The driver sends a specified XOFF character, and completes the request after one of the following events occurs:

A write request is received.

A timer expires (a time-out value is specified by the XOFF counter request).

The serial controller driver receives a number of characters that is greater than or equal to a count specified by the XOFF counter request.

For more information about the operation of an XOFF counter, see the description of the <b>SERIAL_XOFF_COUNTER</b> structure in the Ntddser.h header file in the Microsoft Windows Driver Kit (WDK).



## -ioctlparameters

### -input-buffer
The <b>AssociatedIrp.SystemBuffer</b> points to a client-allocated <b>SERIAL_XOFF_COUNTER</b> structure that is used to input XOFF counter information.


### -input-buffer-length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> is set to the size, in bytes, of a <b>SERIAL_XOFF_COUNTER</b> structure.


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

The <b>Status</b> member is set to one of the <a href="serial_device_control_requests.htm#generic_status_values_for_serial_device_control_requests">Generic Status Values for Serial Device Control Requests</a> or to one of the following request-specific values:



The count value specified for the XOFF counter request is less than zero.

A write request was received.

The request timed out.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl_serial_set_xoff.md">IOCTL_SERIAL_SET_XOFF</a>
</dt>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl_serial_set_xon.md">IOCTL_SERIAL_SET_XON</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_XOFF_COUNTER control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

