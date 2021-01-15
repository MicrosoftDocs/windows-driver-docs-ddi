---
UID: NS:ntddcdrm._CDROM_TOC
title: _CDROM_TOC (ntddcdrm.h)
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_TOC return their output data in this structure followed by a series of TRACK_DATA structures.
old-location: storage\cdrom_toc.htm
tech.root: storage
ms.date: 09/10/2019
keywords: ["CDROM_TOC structure"]
ms.keywords: "*PCDROM_TOC, CDROM_TOC, CDROM_TOC structure [Storage Devices], PCDROM_TOC, PCDROM_TOC structure pointer [Storage Devices], _CDROM_TOC, ntddcdrm/CDROM_TOC, ntddcdrm/PCDROM_TOC, storage.cdrom_toc, structs-CD-ROM_943f0104-ee61-4f40-a1a1-8392a15f3fd1.xml"
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
req.typenames: CDROM_TOC, *PCDROM_TOC
f1_keywords:
 - _CDROM_TOC
 - ntddcdrm/_CDROM_TOC
 - PCDROM_TOC
 - ntddcdrm/PCDROM_TOC
 - CDROM_TOC
 - ntddcdrm/CDROM_TOC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdrm.h
api_name:
 - _CDROM_TOC
 - PCDROM_TOC
 - CDROM_TOC
---

# _CDROM_TOC structure


## -description

Device control IRPs with a control code of [IOCTL_CDROM_READ_TOC_EX](./ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md) and a format of CDROM_READ_TOC_EX_FORMAT_TOC return their output data in this structure followed by a series of [TRACK_DATA](./ns-ntddcdrm-_track_data.md) structures.

## -struct-fields

### -field Length

Indicates the length, in bytes, of the table of contents data. This length value does not include the length of the **Length** member itself.

### -field FirstTrack

Indicates the first track number of the table of contents of the first complete session.

### -field LastTrack

Indicates the last track number of the table of contents of the last complete session.

### -field TrackData

Array of structures of type [TRACK_DATA](./ns-ntddcdrm-_track_data.md) that contain table of contents information for all the sessions on the disc.

## -remarks

The output data contains table of contents information for one or more of the specified sessions.

## -see-also

[CDROM_READ_TOC_EX](./ns-ntddcdrm-_cdrom_read_toc_ex.md)

[IOCTL_CDROM_READ_TOC_EX](./ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md)

[TRACK_DATA](./ns-ntddcdrm-_track_data.md)

