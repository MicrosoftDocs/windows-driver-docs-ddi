---
UID: NI:ntddser.IOCTL_SERIAL_CLR_RTS
title: IOCTL_SERIAL_CLR_RTS
author: windows-driver-content
description: The IOCTL_SERIAL_CLR_RTS request clears the request to send (RTS) control signal.
old-location: serports\ioctl_serial_clr_rts.htm
old-project: serports
ms.assetid: 7ecb357f-ba84-4b3d-b6db-73f6682988b8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: serports.ioctl_serial_clr_rts, IOCTL_SERIAL_CLR_RTS control code [Serial Ports], IOCTL_SERIAL_CLR_RTS, ntddser/IOCTL_SERIAL_CLR_RTS, serref_c6ddd78f-7cea-4358-9c02-9c211399f6c8.xml
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
-	IOCTL_SERIAL_CLR_RTS
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_CLR_RTS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_SERIAL_CLR_RTS</b> request clears the <i>request to send</i> (RTS) control signal.

To set RTS, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_rts.md">IOCTL_SERIAL_SET_RTS</a> request.

If the handshake flow control of the device is configured to automatically use RTS, a client cannot clear or set RTS.


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




#### -The Status member is set to one of the Generic Status Values for Serial Device Control Requests. A status of STATUS_INVALID_PARAMETER indicates that the handshake flow control of the device is set to automatically use RTS.


## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_set_rts.md">IOCTL_SERIAL_SET_RTS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_CLR_RTS control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

