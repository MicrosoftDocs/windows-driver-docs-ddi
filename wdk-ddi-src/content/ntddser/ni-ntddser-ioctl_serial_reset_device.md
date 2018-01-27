---
UID: NI:ntddser.IOCTL_SERIAL_RESET_DEVICE
title: IOCTL_SERIAL_RESET_DEVICE
author: windows-driver-content
description: The IOCTL_SERIAL_RESET_DEVICE request resets a serial device.
old-location: serports\ioctl_serial_reset_device.htm
old-project: serports
ms.assetid: af7482b4-4622-40b7-af7a-c952813e7095
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.ioctl_serial_reset_device, IOCTL_SERIAL_RESET_DEVICE control code [Serial Ports], IOCTL_SERIAL_RESET_DEVICE, ntddser/IOCTL_SERIAL_RESET_DEVICE, serref_8c489e42-94d9-4a10-9336-dae4adea904a.xml
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
-	IOCTL_SERIAL_RESET_DEVICE
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_RESET_DEVICE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_SERIAL_RESET_DEVICE</b> request resets a serial device.


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

