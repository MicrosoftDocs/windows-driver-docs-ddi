---
UID: NS:ntddser._SERIAL_BAUD_RATE
title: "_SERIAL_BAUD_RATE"
author: windows-driver-content
description: The SERIAL_BAUD_RATE structure specifies the baud rate at which a serial port is currently configured to transmit and receive data.
old-location: serports\serial_baud_rate.htm
old-project: serports
ms.assetid: 1534B7AC-8968-4AE2-A871-D8F4D4E45CA1
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSERIAL_BAUD_RATE, PSERIAL_BAUD_RATE, PSERIAL_BAUD_RATE structure pointer [Serial Ports], SERIAL_BAUD_RATE, SERIAL_BAUD_RATE structure [Serial Ports], _SERIAL_BAUD_RATE, ntddser/PSERIAL_BAUD_RATE, ntddser/SERIAL_BAUD_RATE, serports.serial_baud_rate"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddser.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 2000.
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
-	SERIAL_BAUD_RATE
product: Windows
targetos: Windows
req.typenames: SERIAL_BAUD_RATE, *PSERIAL_BAUD_RATE
---

# _SERIAL_BAUD_RATE structure


## -description


The <b>SERIAL_BAUD_RATE</b> structure specifies the baud rate at which a serial port is currently configured to transmit and receive data.


## -syntax


````
typedef struct _SERIAL_BAUD_RATE {
  ULONG BaudRate;
} SERIAL_BAUD_RATE, *PSERIAL_BAUD_RATE;
````


## -struct-fields




### -field BaudRate

The baud rate. This parameter specifies the number of bits per second that a serial port is currently configured to transmit or receive. For example, a <b>BaudRate</b> value of 115200 indicates that the port is configured to transfer 115,200 bits per second.


## -remarks



The <a href="..\ntddser\ni-ntddser-ioctl_serial_get_baud_rate.md">IOCTL_SERIAL_GET_BAUD_RATE</a> and <a href="..\ntddser\ni-ntddser-ioctl_serial_set_baud_rate.md">IOCTL_SERIAL_SET_BAUD_RATE</a> I/O control requests use the <b>SERIAL_BAUD_RATE</b> structure to specify the baud rate of a serial port. The <b>IOCTL_SERIAL_SET_BAUD_RATE</b> request configures a serial port to operate at a specified baud rate. The <b>IOCTL_SERIAL_GET_BAUD_RATE</b> request queries a serial port for the baud rate that it is currently configured to operate at.

For more information about some of the possible baud rates that a serial controller driver might support, see the description of the <b>MaxBaud</b> member in <a href="..\ntddser\ns-ntddser-_serial_commprop.md">SERIAL_COMMPROP</a>.




## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_set_baud_rate.md">IOCTL_SERIAL_SET_BAUD_RATE</a>



<a href="..\ntddser\ni-ntddser-ioctl_serial_get_baud_rate.md">IOCTL_SERIAL_GET_BAUD_RATE</a>



<a href="..\ntddser\ns-ntddser-_serial_commprop.md">SERIAL_COMMPROP</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERIAL_BAUD_RATE structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

