---
UID: NS:ntddcdrm.__RAW_READ_INFO
title: __RAW_READ_INFO
author: windows-driver-content
description: The RAW_READ_INFO structure is used in conjunction with the IOCTL_CDROM_RAW_READ request to read data from a CD-ROM in raw mode.
old-location: storage\raw_read_info.htm
old-project: storage
ms.assetid: 8786545d-39b2-4331-9d62-3b345eb58d1f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: __RAW_READ_INFO, *PRAW_READ_INFO, RAW_READ_INFO
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
req.alt-api: RAW_READ_INFO
req.alt-loc: ntddcdrm.h
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
req.typenames: *PRAW_READ_INFO, RAW_READ_INFO
---

# __RAW_READ_INFO structure



## -description
The RAW_READ_INFO structure is used in conjunction with the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_raw_read.md">IOCTL_CDROM_RAW_READ</a> request to read data from a CD-ROM in raw mode.  



## -syntax

````
typedef struct __RAW_READ_INFO {
  LARGE_INTEGER   DiskOffset;
  ULONG           SectorCount;
  TRACK_MODE_TYPE TrackMode;
} RAW_READ_INFO, *PRAW_READ_INFO;
````


## -struct-fields

### -field DiskOffset

Contains an offset into the CD-ROM disc where data will be read. You can  calculate this offset by multiplying the starting sector number for the request times 2048.


### -field SectorCount

Contains the number of sectors to read.


### -field TrackMode

Contains an enumerator of type <a href="..\ntddcdrm\ne-ntddcdrm-_track_mode_type.md">TRACK_MODE_TYPE</a> that indicates the type of the track mode. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_raw_read.md">IOCTL_CDROM_RAW_READ</a>
</dt>
<dt>
<a href="..\ntddcdrm\ne-ntddcdrm-_track_mode_type.md">TRACK_MODE_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RAW_READ_INFO structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

