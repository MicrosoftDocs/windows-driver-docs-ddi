---
UID: NI:ntddcdrm.IOCTL_CDROM_SEEK_AUDIO_MSF
title: IOCTL_CDROM_SEEK_AUDIO_MSF (ntddcdrm.h)
description: Moves the heads to the specified MSF on the media. Obsolete, beginning with Windows Vista.
old-location: storage\ioctl_cdrom_seek_audio_msf.htm
tech.root: storage
ms.assetid: 081a5d8d-7cc7-4499-9360-dfaa5a7c436b
ms.date: 03/29/2018
keywords: ["IOCTL_CDROM_SEEK_AUDIO_MSF IOCTL"]
ms.keywords: IOCTL_CDROM_SEEK_AUDIO_MSF, IOCTL_CDROM_SEEK_AUDIO_MSF control, IOCTL_CDROM_SEEK_AUDIO_MSF control code [Storage Devices], k307_4c88dbd2-30ef-41aa-9330-57319605ec88.xml, ntddcdrm/IOCTL_CDROM_SEEK_AUDIO_MSF, storage.ioctl_cdrom_seek_audio_msf
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
 - IOCTL_CDROM_SEEK_AUDIO_MSF
 - ntddcdrm/IOCTL_CDROM_SEEK_AUDIO_MSF
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdrm.h
api_name:
 - IOCTL_CDROM_SEEK_AUDIO_MSF
---

# IOCTL_CDROM_SEEK_AUDIO_MSF IOCTL


## -description

Moves the heads to the specified MSF on the media.  Obsolete, beginning with Windows Vista.

## -ioctlparameters

### -input-buffer

The buffer at <i>Irp->AssociatedIrp.SystemBuffer</i> contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_seek_audio_msf">CDROM_SEEK_AUDIO_MSF</a> specification.

### -input-buffer-length

<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL, STATUS_INVALID_DEVICE_REQUEST, STATUS_IO_DEVICE_ERROR, STATUS_NO_MEDIA_IN_DEVICE, STATUS_DEVICE_NOT_READY, STATUS_IO_TIME_OUT, or STATUS_VERIFY_REQUIRED.

## -remarks

Beginning with Windows Vista, CDROM class drivers do not use this IOCTL. Prior to Windows Vista, this IOCTL was used for audio playback on older CD-ROM drives that supported direct audio output in hardware.

Client applications should use the <i>Media Control Interface (MCI) API</i> rather than issuing this IOCTL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_seek_audio_msf">CDROM_SEEK_AUDIO_MSF</a>

