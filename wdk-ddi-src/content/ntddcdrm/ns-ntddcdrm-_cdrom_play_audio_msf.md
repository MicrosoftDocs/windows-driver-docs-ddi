---
UID: NS:ntddcdrm._CDROM_PLAY_AUDIO_MSF
title: _CDROM_PLAY_AUDIO_MSF (ntddcdrm.h)
description: Device control IRPs with a control code of IOCTL_CDROM_PLAY_AUDIO_MSF use this structure to play an audio CD.
old-location: storage\cdrom_play_audio_msf.htm
tech.root: storage
ms.assetid: 73589397-9b2b-4d49-9860-cb2eb6a26632
ms.date: 03/29/2018
keywords: ["_CDROM_PLAY_AUDIO_MSF structure"]
ms.keywords: "*PCDROM_PLAY_AUDIO_MSF, CDROM_PLAY_AUDIO_MSF, CDROM_PLAY_AUDIO_MSF structure [Storage Devices], PCDROM_PLAY_AUDIO_MSF, PCDROM_PLAY_AUDIO_MSF structure pointer [Storage Devices], _CDROM_PLAY_AUDIO_MSF, ntddcdrm/CDROM_PLAY_AUDIO_MSF, ntddcdrm/PCDROM_PLAY_AUDIO_MSF, storage.cdrom_play_audio_msf, structs-CD-ROM_27bfe732-1972-4101-baa1-e9d520c3dfcf.xml"
f1_keywords:
 - "ntddcdrm/CDROM_PLAY_AUDIO_MSF"
 - "CDROM_PLAY_AUDIO_MSF"
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
- CDROM_PLAY_AUDIO_MSF
targetos: Windows
req.typenames: CDROM_PLAY_AUDIO_MSF, *PCDROM_PLAY_AUDIO_MSF
---

# _CDROM_PLAY_AUDIO_MSF structure


## -description


Device control IRPs with a control code of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_play_audio_msf">IOCTL_CDROM_PLAY_AUDIO_MSF</a> use this structure to play an audio CD.


## -struct-fields




### -field StartingM

Contains an integer between 0 and 74 that indicates the starting minute. 


### -field StartingS

Contains an integer between 0 and 59 that indicates the starting second. 


### -field StartingF

Contains an integer between 0 and 74 that indicates the starting frame. 


### -field EndingM

Contains an integer between 0 and 74 that indicates the ending minute. 


### -field EndingS

Contains an integer between 0 and 59 that indicates the ending second. 


### -field EndingF

Contains an integer between 0 and 74 that indicates the ending frame.


## -remarks



Device control IRPs with a control code of IOCTL_CDROM_PLAY_AUDIO_MSF use this structure to play an audio CD and to indicate where to begin playing and where to stop. Starting and ending points are indicated in terms of minutes, seconds, and frames.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_play_audio_msf">IOCTL_CDROM_PLAY_AUDIO_MSF</a>
 

 

