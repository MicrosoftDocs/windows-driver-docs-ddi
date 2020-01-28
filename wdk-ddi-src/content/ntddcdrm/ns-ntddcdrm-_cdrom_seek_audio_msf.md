---
UID: NS:ntddcdrm._CDROM_SEEK_AUDIO_MSF
title: _CDROM_SEEK_AUDIO_MSF (ntddcdrm.h)
description: The CDROM_SEEK_AUDIO_MSF structure contains the minute, second, and frame that the device must seek to upon receipt of a device control IRP with a control code of IOCTL_CDROM_SEEK_AUDIO_MSF.
old-location: storage\cdrom_seek_audio_msf.htm
tech.root: storage
ms.assetid: 8fd4e642-5ed4-409e-bcc2-94d309a1e04c
ms.date: 03/29/2018
ms.keywords: "*PCDROM_SEEK_AUDIO_MSF, CDROM_SEEK_AUDIO_MSF, CDROM_SEEK_AUDIO_MSF structure [Storage Devices], PCDROM_SEEK_AUDIO_MSF, PCDROM_SEEK_AUDIO_MSF structure pointer [Storage Devices], _CDROM_SEEK_AUDIO_MSF, ntddcdrm/CDROM_SEEK_AUDIO_MSF, ntddcdrm/PCDROM_SEEK_AUDIO_MSF, storage.cdrom_seek_audio_msf, structs-CD-ROM_1e8a9382-37c6-4473-831e-3547774a5b9d.xml"
f1_keywords:
 - "ntddcdrm/CDROM_SEEK_AUDIO_MSF"
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
- CDROM_SEEK_AUDIO_MSF
product:
- Windows
targetos: Windows
req.typenames: CDROM_SEEK_AUDIO_MSF, *PCDROM_SEEK_AUDIO_MSF
---

# _CDROM_SEEK_AUDIO_MSF structure


## -description


The CDROM_SEEK_AUDIO_MSF structure contains the minute, second, and frame that the device must seek to upon receipt of a device control IRP with a control code of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_seek_audio_msf">IOCTL_CDROM_SEEK_AUDIO_MSF</a>. 


## -struct-fields




### -field M

Contains an integer between 0 and 74 that indicates the minute to seek to.


### -field S

Contains an integer between 0 and 59 that indicates the second to seek to.


### -field F

Contains an integer between 0 and 74 that indicates the frame to seek to.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_seek_audio_msf">IOCTL_CDROM_SEEK_AUDIO_MSF</a>
 

 

