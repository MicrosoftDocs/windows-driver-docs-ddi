---
UID: NS:ntddcdrm._VOLUME_CONTROL
title: _VOLUME_CONTROL (ntddcdrm.h)
description: The VOLUME_CONTROL structure is used in conjunction with the IOCTL_CDROM_GET_VOLUME request to retrieve volume values for up to four audio ports.
old-location: storage\volume_control.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["VOLUME_CONTROL structure"]
ms.keywords: "*PVOLUME_CONTROL, PVOLUME_CONTROL, PVOLUME_CONTROL structure pointer [Storage Devices], VOLUME_CONTROL, VOLUME_CONTROL structure [Storage Devices], _VOLUME_CONTROL, ntddcdrm/PVOLUME_CONTROL, ntddcdrm/VOLUME_CONTROL, storage.volume_control, structs-CD-ROM_d0d59b00-4eb3-4e98-b164-cb8f3e11de31.xml"
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
targetos: Windows
req.typenames: VOLUME_CONTROL, *PVOLUME_CONTROL
f1_keywords:
 - _VOLUME_CONTROL
 - ntddcdrm/_VOLUME_CONTROL
 - PVOLUME_CONTROL
 - ntddcdrm/PVOLUME_CONTROL
 - VOLUME_CONTROL
 - ntddcdrm/VOLUME_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdrm.h
api_name:
 - VOLUME_CONTROL
---

# _VOLUME_CONTROL structure


## -description

The VOLUME_CONTROL structure is used in conjunction with the <a href="/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_volume">IOCTL_CDROM_GET_VOLUME</a> request to retrieve volume values for up to four audio ports.

## -struct-fields

### -field PortVolume

Pointer to an array of volume values, one for each of the ports, with a maximum of four ports.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_volume">IOCTL_CDROM_GET_VOLUME</a>
