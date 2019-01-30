---
UID: NS:ntddcdrm._CDROM_TOC
title: "_CDROM_TOC" (ntddcdrm.h)
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_TOC return their output data in this structure followed by a series of TRACK_DATA structures.
old-location: storage\cdrom_toc.htm
tech.root: storage
ms.assetid: 84312199-5055-41a1-9aa2-4ee91a15d5bf
ms.date: 03/29/2018
ms.keywords: "*PCDROM_TOC, CDROM_TOC, CDROM_TOC structure [Storage Devices], PCDROM_TOC, PCDROM_TOC structure pointer [Storage Devices], _CDROM_TOC, ntddcdrm/CDROM_TOC, ntddcdrm/PCDROM_TOC, storage.cdrom_toc, structs-CD-ROM_943f0104-ee61-4f40-a1a1-8392a15f3fd1.xml"
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
-	CDROM_TOC
product:
- Windows
targetos: Windows
req.typenames: CDROM_TOC, *PCDROM_TOC
---

# _CDROM_TOC structure


## -description


Device control IRPs with a control code of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559367">IOCTL_CDROM_READ_TOC_EX</a> and a format of CDROM_READ_TOC_EX_FORMAT_TOC return their output data in this structure followed by a series of <a href="https://msdn.microsoft.com/library/windows/hardware/ff567982">TRACK_DATA</a> structures.  


## -struct-fields




### -field Length

Indicates the length, in bytes, of the table of contents data. This length value does not include the length of the <b>Length </b>member itself. 


### -field FirstTrack

Indicates the first track number of the table of contents of the first complete session. 


### -field LastTrack

Indicates the last track number of the table of contents of the last complete session.


### -field TrackData

Pointer to an array of structures of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff567982">TRACK_DATA</a> that contain table of contents information for all the sessions on the disc.


## -remarks



The output data contains table of contents information for one or more of the specified sessions.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551366">CDROM_READ_TOC_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559367">IOCTL_CDROM_READ_TOC_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567982">TRACK_DATA</a>
 

 

