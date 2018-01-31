---
UID: NS:ntddcdrm._CDROM_TOC
title: "_CDROM_TOC"
author: windows-driver-content
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_TOC return their output data in this structure followed by a series of TRACK_DATA structures.
old-location: storage\cdrom_toc.htm
old-project: storage
ms.assetid: 84312199-5055-41a1-9aa2-4ee91a15d5bf
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PCDROM_TOC, ntddcdrm/PCDROM_TOC, CDROM_TOC structure [Storage Devices], PCDROM_TOC structure pointer [Storage Devices], PCDROM_TOC, ntddcdrm/CDROM_TOC, _CDROM_TOC, storage.cdrom_toc, CDROM_TOC, structs-CD-ROM_943f0104-ee61-4f40-a1a1-8392a15f3fd1.xml"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddcdrm.h
apiname:
-	CDROM_TOC
product: Windows
targetos: Windows
req.typenames: CDROM_TOC, *PCDROM_TOC
---

# _CDROM_TOC structure


## -description


Device control IRPs with a control code of <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a> and a format of CDROM_READ_TOC_EX_FORMAT_TOC return their output data in this structure followed by a series of <a href="..\ntddcdrm\ns-ntddcdrm-_track_data.md">TRACK_DATA</a> structures.  


## -syntax


````
typedef struct _CDROM_TOC {
  UCHAR      Length[2];
  UCHAR      FirstTrack;
  UCHAR      LastTrack;
  TRACK_DATA TrackData[MAXIMUM_NUMBER_TRACKS];
} CDROM_TOC, *PCDROM_TOC;
````


## -struct-fields




#### - Length

Indicates the length, in bytes, of the table of contents data. This length value does not include the length of the <b>Length </b>member itself. 


#### - FirstTrack

Indicates the first track number of the table of contents of the first complete session. 


#### - LastTrack

Indicates the last track number of the table of contents of the last complete session.


#### - TrackData

Pointer to an array of structures of type <a href="..\ntddcdrm\ns-ntddcdrm-_track_data.md">TRACK_DATA</a> that contain table of contents information for all the sessions on the disc.


## -remarks


The output data contains table of contents information for one or more of the specified sessions.



## -see-also

<a href="..\ntddcdrm\ns-ntddcdrm-_track_data.md">TRACK_DATA</a>

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_read_toc_ex.md">CDROM_READ_TOC_EX</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_TOC structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

