---
UID: NS:ntddtape._TAPE_SET_MEDIA_PARAMETERS
title: "_TAPE_SET_MEDIA_PARAMETERS"
author: windows-driver-content
description: The TAPE_SET_MEDIA_PARAMETERS structure is used in conjunction with the IOCTL_TAPE_SET_MEDIA_PARAMS request to reset the block size of the media in a tape drive.
old-location: storage\tape_set_media_parameters.htm
old-project: storage
ms.assetid: f038eb24-71d2-414c-ad7c-06cb1fa24070
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: TAPE_SET_MEDIA_PARAMETERS structure [Storage Devices], PTAPE_SET_MEDIA_PARAMETERS, *PTAPE_SET_MEDIA_PARAMETERS, structs-tape_83d386fe-a430-4c8f-af97-2f6c7ecc4b67.xml, storage.tape_set_media_parameters, TAPE_SET_MEDIA_PARAMETERS, ntddtape/PTAPE_SET_MEDIA_PARAMETERS, ntddtape/TAPE_SET_MEDIA_PARAMETERS, _TAPE_SET_MEDIA_PARAMETERS, PTAPE_SET_MEDIA_PARAMETERS structure pointer [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddtape.h
req.include-header: Ntddtape.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddtape.h
apiname:
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




#### - BlockSize

Indicates the requested block size, in bytes, or zero for variable block size in a drive that supports it. 


## -see-also

<a href="..\ntddtape\ni-ntddtape-ioctl_tape_set_media_params.md">IOCTL_TAPE_SET_MEDIA_PARAMS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567953">TapeMiniSetMediaParameters</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_SET_MEDIA_PARAMETERS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

