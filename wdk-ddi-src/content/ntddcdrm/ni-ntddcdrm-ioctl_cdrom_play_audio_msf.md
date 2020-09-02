---
UID: NI:ntddcdrm.IOCTL_CDROM_PLAY_AUDIO_MSF
title: IOCTL_CDROM_PLAY_AUDIO_MSF (ntddcdrm.h)
description: Plays the specified range of the media. Obsolete, beginning with Windows Vista.
old-location: storage\ioctl_cdrom_play_audio_msf.htm
tech.root: storage
ms.assetid: cb88fa6b-e96a-41a9-abcc-9ab28b62954f
ms.date: 03/29/2018
keywords: ["IOCTL_CDROM_PLAY_AUDIO_MSF IOCTL"]
ms.keywords: IOCTL_CDROM_PLAY_AUDIO_MSF, IOCTL_CDROM_PLAY_AUDIO_MSF control, IOCTL_CDROM_PLAY_AUDIO_MSF control code [Storage Devices], k307_dce77286-4efa-4b8b-bb78-2c771bd75727.xml, ntddcdrm/IOCTL_CDROM_PLAY_AUDIO_MSF, storage.ioctl_cdrom_play_audio_msf
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_CDROM_PLAY_AUDIO_MSF
 - ntddcdrm/IOCTL_CDROM_PLAY_AUDIO_MSF
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdrm.h
api_name:
 - IOCTL_CDROM_PLAY_AUDIO_MSF
---

# IOCTL_CDROM_PLAY_AUDIO_MSF IOCTL


## -description

Plays the specified range of the media. Obsolete, beginning with Windows Vista.

## -ioctlparameters

### -input-buffer

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_play_audio_msf">CDROM_PLAY_AUDIO_MSF</a> structure in the buffer at <i>Irp->AssociatedIrp.System</i> contains the starting and ending MSF values.

### -input-buffer-length

<i>Parameters.DeviceIoControl.InputBufferLength</i> in the I/O stack location indicates the size, in bytes, of the buffer, which must be greater than or equal to  <b> sizeof</b>(CDROM_PLAY_AUDIO_MSF).

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_BUFFER_TOO_SMALL, STATUS_DEVICE_NOT_READY, STATUS_IO_DEVICE_ERROR, STATUS_IO_TIME_OUT, or STATUS_VERIFY_REQUIRED.

## -remarks

Beginning with Windows Vista, CDROM class drivers do not use this IOCTL. Prior to Windows Vista, this IOCTL was used for audio playback on older CD-ROM drives that supported direct audio output in hardware.

Client applications should use the <i>Media Control Interface (MCI) API</i> rather than issuing this IOCTL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_play_audio_msf">CDROM_PLAY_AUDIO_MSF</a>

