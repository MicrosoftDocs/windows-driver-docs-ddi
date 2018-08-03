---
UID: NI:ntddser.IOCTL_SERIAL_SET_MODEM_CONTROL
title: IOCTL_SERIAL_SET_MODEM_CONTROL
author: windows-driver-content
description: The IOCTL_SERIAL_SET_MODEM_CONTROL request sets the modem control register (MCR) in the UART. No parameter checking is done on the client-supplied register settings.
old-location: serports\ioctl_serial_set_modem_control.htm
tech.root: serports
ms.assetid: 3ec5c4ab-d5da-44c7-9a62-c25d04dbef41
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_SERIAL_SET_MODEM_CONTROL, IOCTL_SERIAL_SET_MODEM_CONTROL control, IOCTL_SERIAL_SET_MODEM_CONTROL control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_MODEM_CONTROL, serports.ioctl_serial_set_modem_control, serref_a7d7db4d-c889-4a99-b21b-9efb533901a9.xml
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddser.h
api_name:
-	IOCTL_SERIAL_SET_MODEM_CONTROL
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_SET_MODEM_CONTROL IOCTL


## -description


The <b>IOCTL_SERIAL_SET_MODEM_CONTROL</b> request sets the modem control register (MCR) in the UART. No parameter checking is done on the client-supplied register settings.

To obtain the value of the MCR, a client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546591">IOCTL_SERIAL_GET_MODEM_CONTROL</a> request.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated ULONG that is used to input modem control information.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a ULONG.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -remarks



The implementation of this I/O control request (IOCTL) is hardware-specific because no standard layout is defined for the modem control register (MCR) across 16550-compatible UART devices. The drivers for peripheral devices that connect to serial ports should avoid using this IOCTL, which might work with some UARTs but not with others. This IOCTL is primarily used to configure the UART into loopback mode for testing, but only if the UART has an MCR that supports loopback mode.

For an example layout of an MCR, see the definition of the MCR bits (SERIAL_MCR_DTR through SERIAL_MCR_LOOP) in the Serial.h header file in the <a href="http://go.microsoft.com/fwlink/p/?LinkId=617962">Serial driver sample</a> on GitHub.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546591">IOCTL_SERIAL_GET_MODEM_CONTROL</a>
 

 

