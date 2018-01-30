---
UID: NI:ntddser.IOCTL_SERIAL_SET_MODEM_CONTROL
title: IOCTL_SERIAL_SET_MODEM_CONTROL
author: windows-driver-content
description: The IOCTL_SERIAL_SET_MODEM_CONTROL request sets the modem control register (MCR) in the UART. No parameter checking is done on the client-supplied register settings.
old-location: serports\ioctl_serial_set_modem_control.htm
old-project: serports
ms.assetid: 3ec5c4ab-d5da-44c7-9a62-c25d04dbef41
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.ioctl_serial_set_modem_control, IOCTL_SERIAL_SET_MODEM_CONTROL control code [Serial Ports], IOCTL_SERIAL_SET_MODEM_CONTROL, ntddser/IOCTL_SERIAL_SET_MODEM_CONTROL, serref_a7d7db4d-c889-4a99-b21b-9efb533901a9.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddser.h
apiname:
-	IOCTL_SERIAL_SET_MODEM_CONTROL
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_SET_MODEM_CONTROL IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_SERIAL_SET_MODEM_CONTROL</b> request sets the modem control register (MCR) in the UART. No parameter checking is done on the client-supplied register settings.

To obtain the value of the MCR, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_get_modem_control.md">IOCTL_SERIAL_GET_MODEM_CONTROL</a> request.


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


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -remarks


The implementation of this I/O control request (IOCTL) is hardware-specific because no standard layout is defined for the modem control register (MCR) across 16550-compatible UART devices. The drivers for peripheral devices that connect to serial ports should avoid using this IOCTL, which might work with some UARTs but not with others. This IOCTL is primarily used to configure the UART into loopback mode for testing, but only if the UART has an MCR that supports loopback mode.

For an example layout of an MCR, see the definition of the MCR bits (SERIAL_MCR_DTR through SERIAL_MCR_LOOP) in the Serial.h header file in the <a href="http://go.microsoft.com/fwlink/p/?LinkId=617962">Serial driver sample</a> on GitHub.



## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_get_modem_control.md">IOCTL_SERIAL_GET_MODEM_CONTROL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_SET_MODEM_CONTROL control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

