---
UID: NS:minitape._TAPE_GET_MEDIA_PARAMETERS
title: _TAPE_GET_MEDIA_PARAMETERS (minitape.h)
description: The _TAPE_GET_MEDIA_PARAMETERS structure (minitape.h) contains information about the parameters of a tape media.
old-location: storage\tape_get_media_parameters.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["TAPE_GET_MEDIA_PARAMETERS structure"]
ms.keywords: "*PTAPE_GET_MEDIA_PARAMETERS, PTAPE_GET_MEDIA_PARAMETERS, PTAPE_GET_MEDIA_PARAMETERS structure pointer [Storage Devices], TAPE_GET_MEDIA_PARAMETERS, TAPE_GET_MEDIA_PARAMETERS structure [Storage Devices], _TAPE_GET_MEDIA_PARAMETERS, ntddtape/PTAPE_GET_MEDIA_PARAMETERS, ntddtape/TAPE_GET_MEDIA_PARAMETERS, storage.tape_get_media_parameters, structs-tape_19ce668d-65dd-40d6-a668-d34e540cc686.xml"
req.header: minitape.h
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
req.typenames: TAPE_GET_MEDIA_PARAMETERS, *PTAPE_GET_MEDIA_PARAMETERS
f1_keywords:
 - _TAPE_GET_MEDIA_PARAMETERS
 - minitape/_TAPE_GET_MEDIA_PARAMETERS
 - PTAPE_GET_MEDIA_PARAMETERS
 - minitape/PTAPE_GET_MEDIA_PARAMETERS
 - TAPE_GET_MEDIA_PARAMETERS
 - minitape/TAPE_GET_MEDIA_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddtape.h
api_name:
 - _TAPE_GET_MEDIA_PARAMETERS
 - PTAPE_GET_MEDIA_PARAMETERS
 - TAPE_GET_MEDIA_PARAMETERS
---

# _TAPE_GET_MEDIA_PARAMETERS structure (minitape.h)


## -description

The TAPE_GET_MEDIA_PARAMETERS structure is used in conjunction with the <a href="/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetMediaParameters</a> routine to retrieve tape media parameters.

## -struct-fields

### -field Capacity

Indicates the total number of bytes of user data the tape can hold.

### -field Remaining

Indicates the number of bytes from the current position to the end of the tape.

### -field BlockSize

Indicates the block size, in bytes, or zero if the drive is using variable block size.

### -field PartitionCount

Indicates the number of partitions on the tape. If the tape is not partitioned, <b>PartitionCount</b> is 1.

### -field WriteProtected

Is set to <b>TRUE</b> if the tape is write-protected.

## -see-also

<a href="/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetMediaParameters</a>

