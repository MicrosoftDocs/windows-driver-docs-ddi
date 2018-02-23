---
UID: NI:ntddser.IOCTL_SERIAL_GET_LINE_CONTROL
title: IOCTL_SERIAL_GET_LINE_CONTROL
author: windows-driver-content
description: The IOCTL_SERIAL_GET_LINE_CONTROL request returns information about the line control set for a serial device. The line control parameters include the number of stop bits, the number of data bits, and the parity.
old-location: serports\ioctl_serial_get_line_control.htm
old-project: serports
ms.assetid: 72585a00-ee43-44fa-a6f4-baa9fe5a2e3f
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: serports.ioctl_serial_get_line_control, IOCTL_SERIAL_GET_LINE_CONTROL control code [Serial Ports], IOCTL_SERIAL_GET_LINE_CONTROL, ntddser/IOCTL_SERIAL_GET_LINE_CONTROL, serref_46b42112-a960-44dc-8ce7-3c8d68746fe9.xml
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
-	IOCTL_SERIAL_GET_LINE_CONTROL
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_GET_LINE_CONTROL IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_SERIAL_GET_LINE_CONTROL</b> request returns information about the line control set for a serial device. The line control parameters include the number of stop bits, the number of data bits, and the parity.

To configure the line control, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_line_control.md">IOCTL_SERIAL_SET_LINE_CONTROL</a> request.

For information about valid line control register settings, see <a href="..\ntddser\ns-ntddser-_serial_line_control.md">SERIAL_LINE_CONTROL</a>.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_LINE_CONTROL</b> structure that the serial controller driver uses to output information about the line control configuration.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <b>SERIAL_LINE_CONTROL</b> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a <b>SERIAL_LINE_CONTROL</b> structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also

<a href="..\ntddser\ns-ntddser-_serial_line_control.md">SERIAL_LINE_CONTROL</a>



<a href="..\ntddser\ni-ntddser-ioctl_serial_set_line_control.md">IOCTL_SERIAL_SET_LINE_CONTROL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_GET_LINE_CONTROL control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

