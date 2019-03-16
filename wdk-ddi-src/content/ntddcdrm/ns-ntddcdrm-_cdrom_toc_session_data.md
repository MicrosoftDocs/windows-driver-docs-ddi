---
UID: NS:ntddcdrm._CDROM_TOC_SESSION_DATA
title: _CDROM_TOC_SESSION_DATA (ntddcdrm.h)
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_SESSION return their output data in this structure followed by a series of TRACK_DATA structures.
old-location: storage\cdrom_toc_session_data.htm
tech.root: storage
ms.assetid: ba039a22-b1af-4ade-bd99-b7296be4dd42
ms.date: 03/29/2018
ms.keywords: "*PCDROM_TOC_SESSION_DATA, CDROM_TOC_SESSION_DATA, CDROM_TOC_SESSION_DATA structure [Storage Devices], PCDROM_TOC_SESSION_DATA, PCDROM_TOC_SESSION_DATA structure pointer [Storage Devices], _CDROM_TOC_SESSION_DATA, ntddcdrm/CDROM_TOC_SESSION_DATA, ntddcdrm/PCDROM_TOC_SESSION_DATA, storage.cdrom_toc_session_data, structs-CD-ROM_b3bb7380-ca50-4340-bf90-4b6e231bcdbc.xml"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddcdrm.h
api_name:
- CDROM_TOC_SESSION_DATA
product:
- Windows
targetos: Windows
req.typenames: CDROM_TOC_SESSION_DATA, *PCDROM_TOC_SESSION_DATA
---

# _CDROM_TOC_SESSION_DATA structure


## -description


Device control IRPs with a control code of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559367">IOCTL_CDROM_READ_TOC_EX</a> and a format of CDROM_READ_TOC_EX_FORMAT_SESSION return their output data in this structure followed by a series of <a href="https://msdn.microsoft.com/library/windows/hardware/ff567982">TRACK_DATA</a> structures. 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551366">CDROM_READ_TOC_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559367">IOCTL_CDROM_READ_TOC_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567982">TRACK_DATA</a>
 

 

