---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DEVICE_SILO_COMMAND
title: IOCTL_EHSTOR_DEVICE_SILO_COMMAND
author: windows-driver-content
description: This IOCTL issues a silo command to the targeted silo on the device. Both input and output data are structured according to the definition of silo commands, as found in the IEEE 1667 specification document.
old-location: storage\ioctl_ehstor_device_silo_command.htm
old-project: storage
ms.assetid: 3258FA16-E1FE-4CBF-8C87-0C7A8B2A7EBF
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _PDO_TYPE, PDO_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_EHSTOR_DEVICE_SILO_COMMAND
req.alt-loc: EhStorIoctl.h
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
req.typenames: PDO_TYPE
---

# IOCTL_EHSTOR_DEVICE_SILO_COMMAND IOCTL



## -description
This IOCTL issues a silo command to the targeted silo on the device. Both input and output data are structured according to the definition of silo commands, as found in the IEEE 1667 specification document.



## -ioctlparameters

### -input-buffer
The input buffer at Irp-&gt;AssociatedIrp.SystemBuffer must contain a structure of type <a href="..\ehstorioctl\ns-ehstorioctl-tagsilo_command.md">SILO_COMMAND</a>.


### -input-buffer-length
The length of a <a href="..\ehstorioctl\ns-ehstorioctl-tagsilo_command.md">SILO_COMMAND</a> structure.


### -output-buffer
The output buffer contains the output data returned directly from the device response to this silo command. The structure of this output data is assumed to be shared knowledge between the client issuing this IOCTL and the device.


### -output-buffer-length
The length of the buffer.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
One of the following values may be returned in the Status field:


<dl>
<dd>
STATUS_SUCCESS - The silo command was successfully issued to the device.

</dd>
</dl>


STATUS_SUCCESS - The silo command was successfully issued to the device.


<dl>
<dd>
STATUS_INVALID_BUFFER_SIZE - The input buffer length supplied is of incorrect size.

</dd>
</dl>


STATUS_INVALID_BUFFER_SIZE - The input buffer length supplied is of incorrect size.


<dl>
<dd>
STATUS_BUFFER_TOO_SMALL - The output buffer length supplied is of insufficient size to hold the device response for this silo command.

</dd>
</dl>


STATUS_BUFFER_TOO_SMALL - The output buffer length supplied is of insufficient size to hold the device response for this silo command.


## -remarks
