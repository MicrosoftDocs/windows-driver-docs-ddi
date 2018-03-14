---
UID: NS:minitape._TAPE_SET_MEDIA_PARAMETERS
title: "_TAPE_SET_MEDIA_PARAMETERS"
author: windows-driver-content
description: The TAPE_SET_MEDIA_PARAMETERS structure is used in conjunction with the IOCTL_TAPE_SET_MEDIA_PARAMS request to reset the block size of the media in a tape drive.
old-location: storage\tape_set_media_parameters.htm
old-project: storage
ms.assetid: f038eb24-71d2-414c-ad7c-06cb1fa24070
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PTAPE_SET_MEDIA_PARAMETERS, PTAPE_SET_MEDIA_PARAMETERS, PTAPE_SET_MEDIA_PARAMETERS structure pointer [Storage Devices], TAPE_SET_MEDIA_PARAMETERS, TAPE_SET_MEDIA_PARAMETERS structure [Storage Devices], _TAPE_SET_MEDIA_PARAMETERS, ntddtape/PTAPE_SET_MEDIA_PARAMETERS, ntddtape/TAPE_SET_MEDIA_PARAMETERS, storage.tape_set_media_parameters, structs-tape_83d386fe-a430-4c8f-af97-2f6c7ecc4b67.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddtape.h
api_name:
-	TAPE_SET_MEDIA_PARAMETERS
product: Windows
targetos: Windows
req.typenames: TAPE_SET_MEDIA_PARAMETERS, *PTAPE_SET_MEDIA_PARAMETERS
---

# _TAPE_SET_MEDIA_PARAMETERS structure


## -description


The TAPE_SET_MEDIA_PARAMETERS structure is used in conjunction with the <a href="..\ntddtape\ni-ntddtape-ioctl_tape_set_media_params.md">IOCTL_TAPE_SET_MEDIA_PARAMS</a> request to reset the block size of the media in a tape drive.


## -syntax


````
typedef struct _TAPE_SET_MEDIA_PARAMETERS {
  ULONG BlockSize;
} TAPE_SET_MEDIA_PARAMETERS, *PTAPE_SET_MEDIA_PARAMETERS;
````


## -struct-fields




### -field BlockSize

Indicates the requested block size, in bytes, or zero for variable block size in a drive that supports it. 


## -see-also

<a href="..\ntddtape\ni-ntddtape-ioctl_tape_set_media_params.md">IOCTL_TAPE_SET_MEDIA_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567953">TapeMiniSetMediaParameters</a>



 

 


