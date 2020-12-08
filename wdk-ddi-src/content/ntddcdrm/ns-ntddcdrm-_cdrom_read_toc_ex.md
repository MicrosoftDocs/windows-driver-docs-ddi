---
UID: NS:ntddcdrm._CDROM_READ_TOC_EX
title: CDROM_READ_TOC_EX (ntddcdrm.h)
description: When drivers query a target CD-ROM device with IOCTL_CDROM_READ_TOC_EX they must define the query with this structure.
old-location: storage\cdrom_read_toc_ex.htm
tech.root: storage
ms.date: 01/08/2020
keywords: ["CDROM_READ_TOC_EX structure"]
ms.keywords: "*PCDROM_READ_TOC_EX, CDROM_READ_TOC_EX, CDROM_READ_TOC_EX structure [Storage Devices], PCDROM_READ_TOC_EX, PCDROM_READ_TOC_EX structure pointer [Storage Devices], _CDROM_READ_TOC_EX, ntddcdrm/CDROM_READ_TOC_EX, ntddcdrm/PCDROM_READ_TOC_EX, storage.cdrom_read_toc_ex, structs-CD-ROM_b12c5d5a-b319-4122-be7f-721bd384dbf2.xml"
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
req.typenames: CDROM_READ_TOC_EX, *PCDROM_READ_TOC_EX
f1_keywords:
 - _CDROM_READ_TOC_EX
 - ntddcdrm/_CDROM_READ_TOC_EX
 - PCDROM_READ_TOC_EX
 - ntddcdrm/PCDROM_READ_TOC_EX
 - CDROM_READ_TOC_EX
 - ntddcdrm/CDROM_READ_TOC_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdrm.h
api_name:
 - CDROM_READ_TOC_EX
---

# CDROM_READ_TOC_EX structure


## -description

When drivers query a target CD-ROM device with [IOCTL_CDROM_READ_TOC_EX](./ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md) they must define the query with this structure.

## -struct-fields

### -field Format

Specifies table of contents read operation, as follows:

| Operation | Description |
| --------- | ----------- |
| CDROM_READ_TOC_EX_FORMAT_TOC | Query the device for the table of contents for the specified session(s). The **SessionTrack** member of the structure specifies the starting track number of the session for which the data will be returned. For multi-session CD-ROMs, this command will return the table of contents data for all sessions. For track number 0xAA, it returns the lead-out area of the last complete session. The output data is reported in a [CDROM_TOC](./ns-ntddcdrm-_cdrom_toc.md) structure. |
| CDROM_READ_TOC_EX_FORMAT_SESSION | Query the device for the first complete session number, the last complete session number, and the last complete session starting address. The output data is reported in a [CDROM_TOC_SESSION_DATA](./ns-ntddcdrm-_cdrom_toc_session_data.md) structure. With this format, the **SessionTrack** member is reserved and must be set to zero. This format provides the initiator with quick access to the last finalized session starting address. |
| CDROM_READ_TOC_EX_FORMAT_FULL_TOC | Query the device for all Q subcode data in the lead-in table of contents areas starting from the session number specified in the **SessionTrack** member. The output data is reported in a header structure, [CDROM_TOC_FULL_TOC_DATA](./ns-ntddcdrm-_cdrom_toc_full_toc_data.md), followed by a series of track descriptors defined in [CDROM_TOC_FULL_TOC_DATA_BLOCK](./ns-ntddcdrm-_cdrom_toc_full_toc_data_block.md). In this format, logical block addressing (LBA) is not defined, and the **Msf** member must be set to 1. |
| CDROM_READ_TOC_EX_FORMAT_PMA | Query the device for all Q subcode data in the *program memory area* (PMA). The output data is reported in a [CDROM_TOC_PMA_DATA](./ns-ntddcdrm-_cdrom_toc_pma_data.md) structure. In this format, the **SessionTrack** member is reserved and must be set to zero. Logical block addressing (LBA) is not defined, and the **Msf** member must be set to 1. |
| CDROM_READ_TOC_EX_FORMAT_ATIP | Query the device for *absolute time in pregroove* (ATIP) data. The output data is reported in the [CDROM_TOC_ATIP_DATA](./ns-ntddcdrm-_cdrom_toc_atip_data.md) structure. In this format, the **SessionTrack** member is reserved and must be set to zero. Logical block addressing (LBA) is not defined, and the **Msf** member must be set to 1. |
| CDROM_READ_TOC_EX_FORMAT_CDTEXT | Query the device for CD-TEXT information that is recorded in the lead-in area as R-W subchannel data. The output data is reported in a [CDROM_TOC_CD_TEXT_DATA](./ns-ntddcdrm-_cdrom_toc_cd_text_data.md) structure with an appended array of [CDROM_TOC_CD_TEXT_DATA_BLOCK](./ns-ntddcdrm-_cdrom_toc_cd_text_data_block.md) structures. |

### -field Reserved1

Reserved.

### -field Msf

Indicates the minute-second-frame bit. When set to one, this bit indicates that minute-second-frame (MSF) addressing must be used. When zero, it indicates that logical block addressing (LBA) must be used.

### -field SessionTrack

Specifies the starting track number for which the data will be returned, the session for which the command is targeted, or a reserved field that drivers should set to zero. Which of these values **SessionTrack** takes depends on the value of the **Format** member.

### -field Reserved2

Reserved.

### -field Reserved3

Reserved.

## -remarks

For further information and definitions of terms used in this reference page and in the reference pages of related structures, see specification *T10/1363-D*, by National Committee for Information Technology Standards (NCITS).

## -see-also

[CDROM_TOC](./ns-ntddcdrm-_cdrom_toc.md)

[CDROM_TOC_ATIP_DATA](./ns-ntddcdrm-_cdrom_toc_atip_data.md)

[CDROM_TOC_CD_TEXT_DATA](./ns-ntddcdrm-_cdrom_toc_cd_text_data.md)

[CDROM_TOC_CD_TEXT_DATA_BLOCK](./ns-ntddcdrm-_cdrom_toc_cd_text_data_block.md)

[CDROM_TOC_FULL_TOC_DATA](./ns-ntddcdrm-_cdrom_toc_full_toc_data.md)

[CDROM_TOC_FULL_TOC_DATA_BLOCK](./ns-ntddcdrm-_cdrom_toc_full_toc_data_block.md)

[CDROM_TOC_PMA_DATA](./ns-ntddcdrm-_cdrom_toc_pma_data.md)

[CDROM_TOC_SESSION_DATA](./ns-ntddcdrm-_cdrom_toc_session_data.md)

[IOCTL_CDROM_READ_TOC_EX](./ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md)
