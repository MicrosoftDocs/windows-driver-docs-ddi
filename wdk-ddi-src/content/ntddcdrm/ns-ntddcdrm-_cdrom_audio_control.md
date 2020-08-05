---
UID: NS:ntddcdrm._CDROM_AUDIO_CONTROL
title: _CDROM_AUDIO_CONTROL (ntddcdrm.h)
description: The CDROM_AUDIO_CONTROL structure is used in conjunction with the IOCTL_CDROM_GET_CONTROL request to report the audio playback mode.
old-location: storage\cdrom_audio_control.htm
tech.root: storage
ms.assetid: f99ad24d-e1cf-4381-93b9-c10e4b19b401
ms.date: 03/29/2018
keywords: ["CDROM_AUDIO_CONTROL structure"]
ms.keywords: "*PCDROM_AUDIO_CONTROL, CDROM_AUDIO_CONTROL, CDROM_AUDIO_CONTROL structure [Storage Devices], PCDROM_AUDIO_CONTROL, PCDROM_AUDIO_CONTROL structure pointer [Storage Devices], _CDROM_AUDIO_CONTROL, ntddcdrm/CDROM_AUDIO_CONTROL, ntddcdrm/PCDROM_AUDIO_CONTROL, storage.cdrom_audio_control, structs-CD-ROM_aac7f375-669d-4188-94bf-0f61c0fbf376.xml"
f1_keywords:
 - "ntddcdrm/CDROM_AUDIO_CONTROL"
 - "CDROM_AUDIO_CONTROL"
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
- CDROM_AUDIO_CONTROL
targetos: Windows
req.typenames: CDROM_AUDIO_CONTROL, *PCDROM_AUDIO_CONTROL
---

# _CDROM_AUDIO_CONTROL structure


## -description


The CDROM_AUDIO_CONTROL structure is used in conjunction with the IOCTL_CDROM_GET_CONTROL request to report the audio playback mode. 


## -struct-fields




### -field LbaFormat

Contains the logical block address (LBA) format.  


### -field LogicalBlocksPerSecond

Contains the number of logical blocks per second.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_control">IOCTL_CDROM_GET_CONTROL</a>
 

 

