---
UID: NI:ntddser.IOCTL_SERIAL_SET_XON
title: IOCTL_SERIAL_SET_XON
author: windows-driver-content
description: The IOCTL_SERIAL_SET_XON request emulates the reception of a XON (transmit on) character, which restarts reception of data.
old-location: serports\ioctl_serial_set_xon.htm
old-project: serports
ms.assetid: 082a02dc-93c2-495d-bc20-cb3510c00d78
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_SERIAL_SET_XON, IOCTL_SERIAL_SET_XON control, IOCTL_SERIAL_SET_XON control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_XON, serports.ioctl_serial_set_xon, serref_1c7446da-0080-45f4-af38-c674b874883d.xml
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
-	IOCTL_SERIAL_SET_XON
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_SET_XON IOCTL


## -description


The <b>IOCTL_SERIAL_SET_XON</b> request emulates the reception of a XON (transmit on) character, which restarts reception of data.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546784">IOCTL_SERIAL_SET_XOFF</a>
 

 

