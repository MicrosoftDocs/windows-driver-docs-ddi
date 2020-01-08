---
UID: NS:ntddcdrm._TRACK_DATA
title: TRACK_DATA (ntddcdrm.h)
description: Track descriptor is used in conjunction with CDROM_TOC and CDROM_TOC_SESSION_DATA.
old-location: storage\track_data.htm
tech.root: storage
ms.assetid: f412ff4e-6c65-40f8-9747-dc5059e588f6
ms.date: 01/08/2020
ms.keywords: "*PTRACK_DATA, PTRACK_DATA, PTRACK_DATA structure pointer [Storage Devices], TRACK_DATA, TRACK_DATA structure [Storage Devices], _TRACK_DATA, ntddcdrm/PTRACK_DATA, ntddcdrm/TRACK_DATA, storage.track_data, structs-CD-ROM_37ea4578-82b7-4b8e-be1b-28c27de349d9.xml"
ms.topic: struct
f1_keywords:
 - "ntddcdrm/TRACK_DATA"
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
- TRACK_DATA
product:
- Windows
targetos: Windows
req.typenames: TRACK_DATA, *PTRACK_DATA
---

# TRACK_DATA structure

## -description

The TRACK_DATA structure is used in conjunction with [CDROM_TOC](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_toc) and [CDROM_TOC_SESSION_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_toc_session_data).

## -struct-fields

### -field Reserved

Reserved.

### -field Control

Indicates the attributes of the track. For information about the permissible values for this member, see specification *T10/1363-D*, by National Committee for Information Technology Standards (NCITS).

### -field Adr

Indicates the type of information encoded in the Q subchannel of the block where this table of contents entry was found. For information about the permissible values for this member, see specification *T10/1363-D*, by National Committee for Information Technology Standards (NCITS).

### -field TrackNumber

Indicates the number of the track.

### -field Reserved1

Reserved.

### -field Address

Indicates the starting address of the track.

## -remarks

This structure contains table of contents information for a track.

## -see-also

[CDROM_TOC](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_toc)

[CDROM_TOC_SESSION_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_toc_session_data)

[IOCTL_CDROM_READ_TOC_EX](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_read_toc_ex
)
