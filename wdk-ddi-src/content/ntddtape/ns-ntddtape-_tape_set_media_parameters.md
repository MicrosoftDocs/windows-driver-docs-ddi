---
UID: NS:ntddtape._TAPE_SET_MEDIA_PARAMETERS
title: _TAPE_SET_MEDIA_PARAMETERS (ntddtape.h)
description: The TAPE_SET_MEDIA_PARAMETERS structure is used in conjunction with the IOCTL_TAPE_SET_MEDIA_PARAMS request to reset the block size of the media in a tape drive.
old-location: storage\tape_set_media_parameters.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["TAPE_SET_MEDIA_PARAMETERS structure"]
ms.keywords: "*PTAPE_SET_MEDIA_PARAMETERS, PTAPE_SET_MEDIA_PARAMETERS, PTAPE_SET_MEDIA_PARAMETERS structure pointer [Storage Devices], TAPE_SET_MEDIA_PARAMETERS, TAPE_SET_MEDIA_PARAMETERS structure [Storage Devices], _TAPE_SET_MEDIA_PARAMETERS, ntddtape/PTAPE_SET_MEDIA_PARAMETERS, ntddtape/TAPE_SET_MEDIA_PARAMETERS, storage.tape_set_media_parameters, structs-tape_83d386fe-a430-4c8f-af97-2f6c7ecc4b67.xml"
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
req.typenames: TAPE_SET_MEDIA_PARAMETERS, *PTAPE_SET_MEDIA_PARAMETERS
f1_keywords:
 - _TAPE_SET_MEDIA_PARAMETERS
 - ntddtape/_TAPE_SET_MEDIA_PARAMETERS
 - PTAPE_SET_MEDIA_PARAMETERS
 - ntddtape/PTAPE_SET_MEDIA_PARAMETERS
 - TAPE_SET_MEDIA_PARAMETERS
 - ntddtape/TAPE_SET_MEDIA_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddtape.h
api_name:
 - _TAPE_SET_MEDIA_PARAMETERS
 - PTAPE_SET_MEDIA_PARAMETERS
 - TAPE_SET_MEDIA_PARAMETERS
---

# _TAPE_SET_MEDIA_PARAMETERS structure (ntddtape.h)


## -description

The TAPE_SET_MEDIA_PARAMETERS structure is used in conjunction with the <a href="/windows-hardware/drivers/ddi/ntddtape/ni-ntddtape-ioctl_tape_set_media_params">IOCTL_TAPE_SET_MEDIA_PARAMS</a> request to reset the block size of the media in a tape drive.

## -struct-fields

### -field BlockSize

Indicates the requested block size, in bytes, or zero for variable block size in a drive that supports it.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddtape/ni-ntddtape-ioctl_tape_set_media_params">IOCTL_TAPE_SET_MEDIA_PARAMS</a>



<a href="/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniSetMediaParameters</a>

