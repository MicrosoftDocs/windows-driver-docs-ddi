---
UID: NS:ntddcdrm._CDROM_TOC_SESSION_DATA
title: "_CDROM_TOC_SESSION_DATA"
author: windows-driver-content
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_SESSION return their output data in this structure followed by a series of TRACK_DATA structures.
old-location: storage\cdrom_toc_session_data.htm
old-project: storage
ms.assetid: ba039a22-b1af-4ade-bd99-b7296be4dd42
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCDROM_TOC_SESSION_DATA, CDROM_TOC_SESSION_DATA, CDROM_TOC_SESSION_DATA structure [Storage Devices], PCDROM_TOC_SESSION_DATA, PCDROM_TOC_SESSION_DATA structure pointer [Storage Devices], _CDROM_TOC_SESSION_DATA, ntddcdrm/CDROM_TOC_SESSION_DATA, ntddcdrm/PCDROM_TOC_SESSION_DATA, storage.cdrom_toc_session_data, structs-CD-ROM_b3bb7380-ca50-4340-bf90-4b6e231bcdbc.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddcdrm.h
api_name:
-	CDROM_TOC_SESSION_DATA
product: Windows
targetos: Windows
req.typenames: CDROM_TOC_SESSION_DATA, *PCDROM_TOC_SESSION_DATA
---

# _CDROM_TOC_SESSION_DATA structure


## -description


Device control IRPs with a control code of <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a> and a format of CDROM_READ_TOC_EX_FORMAT_SESSION return their output data in this structure followed by a series of <a href="..\ntddcdrm\ns-ntddcdrm-_track_data.md">TRACK_DATA</a> structures. 


## -syntax


````
typedef struct _CDROM_TOC_SESSION_DATA {
  UCHAR      Length[2];
  UCHAR      FirstCompleteSession;
  UCHAR      LastCompleteSession;
  TRACK_DATA TrackData[1];
} CDROM_TOC_SESSION_DATA, *PCDROM_TOC_SESSION_DATA;
````


## -struct-fields




### -field Length

Indicates the length, in bytes, of the table of contents data. This length value does not include the length of the <b>Length </b>member itself. 


### -field FirstCompleteSession

Contains the number of the first complete session. 


### -field LastCompleteSession

Contains the number of the last complete session. 


### -field TrackData

Contains data for the first track of the last finished session. This data includes the starting address and number of the track.


## -see-also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_track_data.md">TRACK_DATA</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_read_toc_ex.md">CDROM_READ_TOC_EX</a>



 

 


