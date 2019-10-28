---
UID: NS:ntddvol._VOLUME_READ_PLEX_INPUT
title: _VOLUME_READ_PLEX_INPUT (ntddvol.h)
description: This structure is used in conjunction with IOCTL_VOLUME_READ_PLEX to read data from a specific plex in a volume.
old-location: storage\volume_read_plex_input.htm
tech.root: storage
ms.assetid: 1d53c658-9912-4912-a74f-f7b93367b9e2
ms.date: 03/29/2018
ms.keywords: "*PVOLUME_READ_PLEX_INPUT, PVOLUME_READ_PLEX_INPUT, PVOLUME_READ_PLEX_INPUT structure pointer [Storage Devices], VOLUME_READ_PLEX_INPUT, VOLUME_READ_PLEX_INPUT structure [Storage Devices], _VOLUME_READ_PLEX_INPUT, ntddvol/PVOLUME_READ_PLEX_INPUT, ntddvol/VOLUME_READ_PLEX_INPUT, storage.volume_read_plex_input, structs-volumemgr_26a6ef07-d18e-45bd-b4c3-532d7daadc5c.xml"
ms.topic: struct
f1_keywords:
 - "ntddvol/VOLUME_READ_PLEX_INPUT"
req.header: ntddvol.h
req.include-header: Ntddvol.h
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
- ntddvol.h
api_name:
- VOLUME_READ_PLEX_INPUT
product:
- Windows
targetos: Windows
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
---

# _VOLUME_READ_PLEX_INPUT structure


## -description


This structure is used in conjunction with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_read_plex">IOCTL_VOLUME_READ_PLEX</a> to read data from a specific <a href="https://docs.microsoft.com/windows-hardware/drivers/">plex</a> in a volume. 


## -struct-fields




### -field ByteOffset

Supplies the start offset, in bytes, relative to the beginning of the volume. This member must be aligned on a 512-byte boundary. 


### -field Length

Supplies the length, in bytes, of the block to be read. This member must be an integer multiple of 512 bytes. 


### -field PlexNumber

Supplies the zero-based plex number. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_read_plex">IOCTL_VOLUME_READ_PLEX</a>
 

 

