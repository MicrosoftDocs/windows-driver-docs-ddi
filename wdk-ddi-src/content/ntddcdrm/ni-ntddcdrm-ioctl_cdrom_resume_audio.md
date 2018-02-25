---
UID: NI:ntddcdrm.IOCTL_CDROM_RESUME_AUDIO
title: IOCTL_CDROM_RESUME_AUDIO
author: windows-driver-content
description: Resumes a suspended audio operation. Obsolete, beginning with Windows Vista.
old-location: storage\ioctl_cdrom_resume_audio.htm
old-project: storage
ms.assetid: 50bf3cf3-5225-45c9-9f14-bfcd84574a83
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IOCTL_CDROM_RESUME_AUDIO, IOCTL_CDROM_RESUME_AUDIO control code [Storage Devices], k307_64959ad0-32bd-4b0d-b1a0-2983efcd74fa.xml, ntddcdrm/IOCTL_CDROM_RESUME_AUDIO, storage.ioctl_cdrom_resume_audio
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: Obsolete, beginning with Windows Vista.
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
-	ntddcdrm.h
apiname:
-	IOCTL_CDROM_RESUME_AUDIO
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_RESUME_AUDIO IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Resumes a suspended audio operation.   Obsolete, beginning with Windows Vista.




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

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST if audio is not currently suspended, STATUS_IO_DEVICE_ERROR, STATUS_NO_MEDIA_IN_DEVICE, STATUS_DEVICE_NOT_READY, STATUS_IO_TIME_OUT, or STATUS_VERIFY_REQUIRED.


## -remarks



Beginning with Windows Vista, CDROM class drivers do not use this IOCTL. Prior to Windows Vista, this IOCTL was used for audio playback on older CD-ROM drives that supported direct audio output in hardware.

Client applications should use the <i>Media Control Interface (MCI) API</i> rather than issuing this IOCTL.



