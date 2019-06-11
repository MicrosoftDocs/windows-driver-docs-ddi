---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_CONTROL
title: IOCTL_CDROM_GET_CONTROL (ntddcdrm.h)
description: This IOCTL request is obsolete. Do not use.Determines the current audio playback mode.
old-location: storage\ioctl_cdrom_get_control.htm
tech.root: storage
ms.assetid: 3d474eb7-6622-48fd-bf40-c17d03933828
ms.date: 03/29/2018
ms.keywords: IOCTL_CDROM_GET_CONTROL, IOCTL_CDROM_GET_CONTROL control, IOCTL_CDROM_GET_CONTROL control code [Storage Devices], k307_441b4747-9431-42c3-b550-39aaea1229f1.xml, ntddcdrm/IOCTL_CDROM_GET_CONTROL, storage.ioctl_cdrom_get_control
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
- ntddcdrm.h
api_name:
- IOCTL_CDROM_GET_CONTROL
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_GET_CONTROL IOCTL


## -description



This IOCTL request is obsolete. Do not use.

Determines the current audio playback mode. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551360">CDROM_AUDIO_CONTROL</a> data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be >= <b>sizeof</b>(CDROM_AUDIO_CONTROL).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL, STATUS_DEVICE_NOT_READY, STATUS_IO_DEVICE_ERROR, STATUS_IO_TIMEOUT, STATUS_INSUFFICIENT_RESOURCES, STATUS_VERIFY_REQUIRED, or STATUS_INVALID_DEVICE_REQUEST.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551360">CDROM_AUDIO_CONTROL</a>
 

 

