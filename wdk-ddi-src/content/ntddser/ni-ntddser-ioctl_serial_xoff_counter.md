---
UID: NI:ntddser.IOCTL_SERIAL_XOFF_COUNTER
title: IOCTL_SERIAL_XOFF_COUNTER (ntddser.h)
description: The IOCTL_SERIAL_XOFF_COUNTER request sets an XOFF counter. An XOFF counter request supports clients that use software to emulate hardware handshake flow control.
old-location: serports\ioctl_serial_xoff_counter.htm
tech.root: serports
ms.assetid: c24451cd-87d7-493d-83cb-2ee96590b8a3
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_XOFF_COUNTER IOCTL"]
ms.keywords: IOCTL_SERIAL_XOFF_COUNTER, IOCTL_SERIAL_XOFF_COUNTER control, IOCTL_SERIAL_XOFF_COUNTER control code [Serial Ports], ntddser/IOCTL_SERIAL_XOFF_COUNTER, serports.ioctl_serial_xoff_counter, serref_ef42292d-d9d2-47be-b368-a696af5d0eea.xml
f1_keywords:
 - "ntddser/IOCTL_SERIAL_XOFF_COUNTER"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddser.h
api_name:
- IOCTL_SERIAL_XOFF_COUNTER
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_XOFF_COUNTER IOCTL


## -description


The <b>IOCTL_SERIAL_XOFF_COUNTER</b> request sets an <i>XOFF counter</i>. An XOFF counter request supports clients that use software to emulate hardware handshake flow control.

An XOFF counter request is synchronized with write requests. The driver sends a specified XOFF character, and completes the request after one of the following events occurs:
<ul>
<li>
A write request is received.

</li>
<li>
A timer expires (a time-out value is specified by the XOFF counter request).

</li>
<li>
The serial controller driver receives a number of characters that is greater than or equal to a count specified by the XOFF counter request.

</li>
</ul>For more information about the operation of an XOFF counter, see the description of the <b>SERIAL_XOFF_COUNTER</b> structure in the Ntddser.h header file in the Microsoft Windows Driver Kit (WDK).


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








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a> or to one of the following request-specific values:




**STATUS_INVALID_PARAMETER**

The count value specified for the XOFF counter request is less than zero.


**STATUS_SERIAL_COUNTER_TIMEOUT**

The request timed out.


**STATUS_SERIAL_MORE_WRITES**

A write request was received.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_xoff">IOCTL_SERIAL_SET_XOFF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_xon">IOCTL_SERIAL_SET_XON</a>
 

 

