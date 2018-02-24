---
UID: NI:ntddser.IOCTL_SERIAL_SET_XOFF
title: IOCTL_SERIAL_SET_XOFF
author: windows-driver-content
description: The IOCTL_SERIAL_SET_XOFF request emulates the reception of an XOFF (transmit off) character.
old-location: serports\ioctl_serial_set_xoff.htm
old-project: serports
ms.assetid: cfddecbd-e225-484f-ba5c-6223a724b414
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: serports.ioctl_serial_set_xoff, IOCTL_SERIAL_SET_XOFF control code [Serial Ports], IOCTL_SERIAL_SET_XOFF, ntddser/IOCTL_SERIAL_SET_XOFF, serref_a2b3591a-cd26-4073-a7ab-af7f2b3f43b6.xml
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
-	IOCTL_SERIAL_SET_XOFF
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_SET_XOFF IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_SERIAL_SET_XOFF</b> request emulates the reception of an XOFF (transmit off) character. The request stops reception of data. If automatic XON/XOFF flow control is not set, then a client <u>must</u> use a subsequent <a href="..\ntddser\ni-ntddser-ioctl_serial_set_xon.md">IOCTL_SERIAL_SET_XON</a> request to restart reception of data.


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

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_set_xon.md">IOCTL_SERIAL_SET_XON</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_SET_XOFF control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

