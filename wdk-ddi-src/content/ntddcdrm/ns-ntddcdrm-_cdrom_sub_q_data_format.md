---
UID: NS:ntddcdrm._CDROM_SUB_Q_DATA_FORMAT
title: _CDROM_SUB_Q_DATA_FORMAT
author: windows-driver-content
description: The CDROM_SUB_Q_DATA_FORMAT structure is used with device control IRPs of type IOCTL_CDROM_READ_Q_CHANNEL.
old-location: storage\cdrom_sub_q_data_format.htm
old-project: storage
ms.assetid: 0eac3cc1-9c1c-4438-ab20-51c65018cea0
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddcdrm/PCDROM_SUB_Q_DATA_FORMAT, PCDROM_SUB_Q_DATA_FORMAT, *PCDROM_SUB_Q_DATA_FORMAT, structs-CD-ROM_1448747c-8b9c-4ccb-8c91-0f8f567f0373.xml, ntddcdrm/CDROM_SUB_Q_DATA_FORMAT, CDROM_SUB_Q_DATA_FORMAT, PCDROM_SUB_Q_DATA_FORMAT structure pointer [Storage Devices], CDROM_SUB_Q_DATA_FORMAT structure [Storage Devices], storage.cdrom_sub_q_data_format, _CDROM_SUB_Q_DATA_FORMAT
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
-	CDROM_SUB_Q_DATA_FORMAT
product: Windows
targetos: Windows
req.typenames: CDROM_SUB_Q_DATA_FORMAT, *PCDROM_SUB_Q_DATA_FORMAT
---

# _CDROM_SUB_Q_DATA_FORMAT structure


## -description


The CDROM_SUB_Q_DATA_FORMAT structure is used with device control IRPs of type <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_q_channel.md">IOCTL_CDROM_READ_Q_CHANNEL</a>. 


## -syntax


````
typedef struct _CDROM_SUB_Q_DATA_FORMAT {
  UCHAR Format;
  UCHAR Track;
} CDROM_SUB_Q_DATA_FORMAT, *PCDROM_SUB_Q_DATA_FORMAT;
````


## -struct-fields




### -field Format

Specifies which subset of the Q data the read operation should return, as follows: 








### -field Track

Indicates the track number where the CD-ROM driver must read the Q subchannel data. If <b>Format</b> is set to IOCTL_CDROM_MEDIA_CATALOG, then the <b>Track</b> member must be set to zero.


##### - Format.IOCTL_CDROM_TRACK_ISRC

Indicates that the read operation should return the ISO/IEC 3901 Track International Standard Recording Code (ISRC). This code gives a unique number to an audio track. If the IOCTL_CDROM_Q_CHANNEL device control IRP specifies this format, the information is returned in the <a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_track_isrc.md">SUB_Q_TRACK_ISRC</a> member of the <a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_channel_data.md">SUB_Q_CHANNEL_DATA</a> structure.


##### - Format.IOCTL_CDROM_CURRENT_POSITION

Indicates that the read operation should return position information such as the track number, the index number, the absolute address, and the track relative address. If the IOCTL_CDROM_Q_CHANNEL device control IRP specifies this format, the information is returned in the <a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_current_position.md">SUB_Q_CURRENT_POSITION</a> member of the <a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_channel_data.md">SUB_Q_CHANNEL_DATA</a> structure.


##### - Format.IOCTL_CDROM_MEDIA_CATALOG

Indicates that the read operation should return the media catalog number. If the IOCTL_CDROM_Q_CHANNEL device control IRP specifies this format, the information is returned in the <a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_media_catalog_number.md">SUB_Q_MEDIA_CATALOG_NUMBER</a> member of the <a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_channel_data.md">SUB_Q_CHANNEL_DATA</a> structure.


## -remarks


The CDROM_SUB_Q_DATA_FORMAT structure indicates the track from which to read the Q part of the subchannel data and the format of the read.



## -see-also

<a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_track_isrc.md">SUB_Q_TRACK_ISRC</a>

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_q_channel.md">IOCTL_CDROM_READ_Q_CHANNEL</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_channel_data.md">SUB_Q_CHANNEL_DATA</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_media_catalog_number.md">SUB_Q_MEDIA_CATALOG_NUMBER</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_current_position.md">SUB_Q_CURRENT_POSITION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_SUB_Q_DATA_FORMAT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

