---
UID: NS:ntddtape._TAPE_GET_POSITION
title: _TAPE_GET_POSITION (ntddtape.h)
description: The TAPE_GET_POSITION structure is used in conjunction with the IOCTL_TAPE_GET_POSITION request to retrieve the current absolute, logical, or pseudological partition and offset position on the tape.
old-location: storage\tape_get_position.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["TAPE_GET_POSITION structure"]
ms.keywords: "*PTAPE_GET_POSITION, PTAPE_GET_POSITION, PTAPE_GET_POSITION structure pointer [Storage Devices], TAPE_GET_POSITION, TAPE_GET_POSITION structure [Storage Devices], _TAPE_GET_POSITION, ntddtape/PTAPE_GET_POSITION, ntddtape/TAPE_GET_POSITION, storage.tape_get_position, structs-tape_e80e5f0f-02d5-4745-a2d1-3d94e8dc9959.xml"
req.header: ntddtape.h
req.include-header: Ntddtape.h, Minitape.h
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
req.typenames: TAPE_GET_POSITION, *PTAPE_GET_POSITION
f1_keywords:
 - _TAPE_GET_POSITION
 - ntddtape/_TAPE_GET_POSITION
 - PTAPE_GET_POSITION
 - ntddtape/PTAPE_GET_POSITION
 - TAPE_GET_POSITION
 - ntddtape/TAPE_GET_POSITION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddtape.h
api_name:
 - _TAPE_GET_POSITION
 - PTAPE_GET_POSITION
 - TAPE_GET_POSITION
---

# _TAPE_GET_POSITION structure (ntddtape.h)


## -description

The TAPE_GET_POSITION structure is used in conjunction with the <a href="/windows-hardware/drivers/ddi/ntddtape/ni-ntddtape-ioctl_tape_get_position">IOCTL_TAPE_GET_POSITION</a> request to retrieve the current absolute, logical, or pseudological partition and offset position on the tape.

## -struct-fields

### -field Type

Indicates the type of position requested. This member can be TAPE_ABSOLUTE_POSITION, TAPE_LOGICAL_POSITION, or TAPE_PSEUDO_LOGICAL_POSITION.

### -field Partition

Indicates the number of the partition where the current position is located.

### -field Offset

Indicates the number of bytes from the beginning of the partition to the current position.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddtape/ni-ntddtape-ioctl_tape_get_position">IOCTL_TAPE_GET_POSITION</a>

