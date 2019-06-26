---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DEVICE_SILO_COMMAND
title: IOCTL_EHSTOR_DEVICE_SILO_COMMAND (ehstorioctl.h)
description: This IOCTL issues a silo command to the targeted silo on the device. Both input and output data are structured according to the definition of silo commands, as found in the IEEE 1667 specification document.
old-location: storage\ioctl_ehstor_device_silo_command.htm
tech.root: storage
ms.assetid: 3258FA16-E1FE-4CBF-8C87-0C7A8B2A7EBF
ms.date: 03/29/2018
ms.keywords: IOCTL_EHSTOR_DEVICE_SILO_COMMAND, IOCTL_EHSTOR_DEVICE_SILO_COMMAND control, IOCTL_EHSTOR_DEVICE_SILO_COMMAND control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DEVICE_SILO_COMMAND, storage.ioctl_ehstor_device_silo_command
ms.topic: ioctl
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- EhStorIoctl.h
api_name:
- IOCTL_EHSTOR_DEVICE_SILO_COMMAND
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_EHSTOR_DEVICE_SILO_COMMAND IOCTL


## -description


This IOCTL issues a silo command to the targeted silo on the device. Both input and output data are structured according to the definition of silo commands, as found in the IEEE 1667 specification document.


## -ioctlparameters




### -input-buffer

The input buffer at Irp->AssociatedIrp.SystemBuffer must contain a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ehstorioctl/ns-ehstorioctl-tagsilo_command">SILO_COMMAND</a>.


### -input-buffer-length

The length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ehstorioctl/ns-ehstorioctl-tagsilo_command">SILO_COMMAND</a> structure.


### -output-buffer

The output buffer contains the output data returned directly from the device response to this silo command. The structure of this output data is assumed to be shared knowledge between the client issuing this IOCTL and the device.


### -output-buffer-length

The length of the buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

One of the following values may be returned in the Status field:


<dl>
<dd>
STATUS_SUCCESS - The silo command was successfully issued to the device.

</dd>
</dl>



<dl>
<dd>
STATUS_INVALID_BUFFER_SIZE - The input buffer length supplied is of incorrect size.

</dd>
</dl>



<dl>
<dd>
STATUS_BUFFER_TOO_SMALL - The output buffer length supplied is of insufficient size to hold the device response for this silo command.

</dd>
</dl>


