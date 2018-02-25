---
UID: NI:ntddser.IOCTL_SERIAL_SET_DTR
title: IOCTL_SERIAL_SET_DTR
author: windows-driver-content
description: The IOCTL_SERIAL_SET_DTR request sets DTR (data terminal ready).
old-location: serports\ioctl_serial_set_dtr.htm
old-project: serports
ms.assetid: cec61f34-389b-43a9-9b24-d42779c018d2
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_SET_DTR, IOCTL_SERIAL_SET_DTR control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_DTR, serports.ioctl_serial_set_dtr, serref_6af1af3b-1345-41df-8dcf-66ec296c27f8.xml
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
-	IOCTL_SERIAL_SET_DTR
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_SET_DTR IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_SERIAL_SET_DTR</b> request sets DTR (data terminal ready).

If the handshake flow control of the device is configured to automatically use DTR, a client cannot clear or set DTR.

To clear DTR, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_clr_dtr.md">IOCTL_SERIAL_CLR_DTR</a> request.


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

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that the handshake flow control of the device is set to automatically use DTR.


## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_clr_dtr.md">IOCTL_SERIAL_CLR_DTR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_SET_DTR control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

