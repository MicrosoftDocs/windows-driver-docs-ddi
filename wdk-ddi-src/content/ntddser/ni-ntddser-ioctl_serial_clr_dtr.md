---
UID: NI:ntddser.IOCTL_SERIAL_CLR_DTR
title: IOCTL_SERIAL_CLR_DTR
author: windows-driver-content
description: The IOCTL_SERIAL_CLR_DTR request clears the data terminal ready (DTR) control signal.
old-location: serports\ioctl_serial_clr_dtr.htm
old-project: serports
ms.assetid: e537c39a-4f79-4854-91df-7a08346c17ea
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_SERIAL_CLR_DTR, IOCTL_SERIAL_CLR_DTR control, IOCTL_SERIAL_CLR_DTR control code [Serial Ports], ntddser/IOCTL_SERIAL_CLR_DTR, serports.ioctl_serial_clr_dtr, serref_37ec12d3-15ad-4a49-90c7-766ffb3943f7.xml
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
-	IOCTL_SERIAL_CLR_DTR
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_CLR_DTR IOCTL


## -description


The <b>IOCTL_SERIAL_CLR_DTR</b> request clears the <i>data terminal ready</i> (DTR) control signal.

To set DTR, a client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546696">IOCTL_SERIAL_SET_DTR</a> request.

If the handshake flow control of the device is configured to automatically use DTR, a client cannot clear or set DTR.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546696">IOCTL_SERIAL_SET_DTR</a>
 

 

