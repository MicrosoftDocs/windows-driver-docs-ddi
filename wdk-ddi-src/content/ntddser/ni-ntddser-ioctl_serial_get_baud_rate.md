---
UID: NI:ntddser.IOCTL_SERIAL_GET_BAUD_RATE
title: IOCTL_SERIAL_GET_BAUD_RATE
author: windows-driver-content
description: The IOCTL_SERIAL_GET_BAUD_RATE request returns the baud rate at which the serial port is currently configured to transmit and receive data.
old-location: serports\ioctl_serial_get_baud_rate.htm
old-project: serports
ms.assetid: 074ab68e-7cd5-44e4-b3f6-2d6ddc5f3095
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.ioctl_serial_get_baud_rate, IOCTL_SERIAL_GET_BAUD_RATE control code [Serial Ports], IOCTL_SERIAL_GET_BAUD_RATE, ntddser/IOCTL_SERIAL_GET_BAUD_RATE, serref_d3a435b0-2934-465a-9c60-91210895755e.xml
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
-	IOCTL_SERIAL_GET_BAUD_RATE
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_GET_BAUD_RATE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_SERIAL_GET_BAUD_RATE</b> request returns the baud rate at which the serial port is currently configured to transmit and receive data.

To set the baud rate, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_baud_rate.md">IOCTL_SERIAL_SET_BAUD_RATE</a> request.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_BAUD_RATE</b> structure that the serial controller driver uses to output the baud rate information.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size in bytes of a <a href="..\ntddser\ns-ntddser-_serial_baud_rate.md">SERIAL_BAUD_RATE</a> structure.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

If the request is successful, the <b>Information</b> member is set to the size in bytes of a <a href="..\ntddser\ns-ntddser-_serial_baud_rate.md">SERIAL_BAUD_RATE</a> structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_set_baud_rate.md">IOCTL_SERIAL_SET_BAUD_RATE</a>

<a href="..\ntddser\ns-ntddser-_serial_baud_rate.md">SERIAL_BAUD_RATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_GET_BAUD_RATE control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

