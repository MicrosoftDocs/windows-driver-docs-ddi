---
UID: NS:ntddcdrm._SUB_Q_TRACK_ISRC
title: _SUB_Q_TRACK_ISRC (ntddcdrm.h)
description: The SUB_Q_TRACK_ISC contains position information and is used in conjunction with the SUB_Q_CHANNEL_DATA structure.
old-location: storage\sub_q_track_isrc.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SUB_Q_TRACK_ISRC structure"]
ms.keywords: "*PSUB_Q_TRACK_ISRC, PSUB_Q_TRACK_ISRC, PSUB_Q_TRACK_ISRC structure pointer [Storage Devices], SUB_Q_TRACK_ISRC, SUB_Q_TRACK_ISRC structure [Storage Devices], _SUB_Q_TRACK_ISRC, ntddcdrm/PSUB_Q_TRACK_ISRC, ntddcdrm/SUB_Q_TRACK_ISRC, storage.sub_q_track_isrc, structs-CD-ROM_372ebccd-64cd-4f5d-a59c-de75c5ffe112.xml"
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
req.typenames: SUB_Q_TRACK_ISRC, *PSUB_Q_TRACK_ISRC
f1_keywords:
 - _SUB_Q_TRACK_ISRC
 - ntddcdrm/_SUB_Q_TRACK_ISRC
 - PSUB_Q_TRACK_ISRC
 - ntddcdrm/PSUB_Q_TRACK_ISRC
 - SUB_Q_TRACK_ISRC
 - ntddcdrm/SUB_Q_TRACK_ISRC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdrm.h
api_name:
 - SUB_Q_TRACK_ISRC
---

# _SUB_Q_TRACK_ISRC structure


## -description

The SUB_Q_TRACK_ISC contains position information and is used in conjunction with the <a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_channel_data">SUB_Q_CHANNEL_DATA</a> structure.

## -struct-fields

### -field Header

Indicates, among other things, the length of the Q subchannel data that was retrieved. See <a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_header">SUB_Q_HEADER</a> for further details.

### -field FormatCode

Should have a value of IOCTL_CDROM_TRACK_ISRC.

### -field Reserved0

Reserved.

### -field Track

Contains the number for the track for which the ISRC value was requested.

### -field Reserved1

Reserved.

### -field Reserved2

Reserved.

### -field Tcval

Indicates that ISRC data was detected, if set to 1. Otherwise, if set to zero, indicates that <b>TrackIsrc</b> is invalid.

### -field TrackIsrc

Contains an array that holds the tracking ISRC data.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_sub_q_data_format">CDROM_SUB_Q_DATA_FORMAT</a>



<a href="/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_read_q_channel">IOCTL_CDROM_READ_Q_CHANNEL</a>



<a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_channel_data">SUB_Q_CHANNEL_DATA</a>



<a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_header">SUB_Q_HEADER</a>
