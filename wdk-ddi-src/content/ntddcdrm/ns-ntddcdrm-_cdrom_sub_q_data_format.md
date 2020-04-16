---
UID: NS:ntddcdrm._CDROM_SUB_Q_DATA_FORMAT
title: _CDROM_SUB_Q_DATA_FORMAT (ntddcdrm.h)
description: The CDROM_SUB_Q_DATA_FORMAT structure is used with device control IRPs of type IOCTL_CDROM_READ_Q_CHANNEL.
old-location: storage\cdrom_sub_q_data_format.htm
tech.root: storage
ms.assetid: 0eac3cc1-9c1c-4438-ab20-51c65018cea0
ms.date: 03/29/2018
keywords: ["_CDROM_SUB_Q_DATA_FORMAT structure"]
ms.keywords: "*PCDROM_SUB_Q_DATA_FORMAT, CDROM_SUB_Q_DATA_FORMAT, CDROM_SUB_Q_DATA_FORMAT structure [Storage Devices], PCDROM_SUB_Q_DATA_FORMAT, PCDROM_SUB_Q_DATA_FORMAT structure pointer [Storage Devices], _CDROM_SUB_Q_DATA_FORMAT, ntddcdrm/CDROM_SUB_Q_DATA_FORMAT, ntddcdrm/PCDROM_SUB_Q_DATA_FORMAT, storage.cdrom_sub_q_data_format, structs-CD-ROM_1448747c-8b9c-4ccb-8c91-0f8f567f0373.xml"
f1_keywords:
 - "ntddcdrm/CDROM_SUB_Q_DATA_FORMAT"
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
- CDROM_SUB_Q_DATA_FORMAT
product:
- Windows
targetos: Windows
req.typenames: CDROM_SUB_Q_DATA_FORMAT, *PCDROM_SUB_Q_DATA_FORMAT
---

# _CDROM_SUB_Q_DATA_FORMAT structure


## -description


The CDROM_SUB_Q_DATA_FORMAT structure is used with device control IRPs of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_read_q_channel">IOCTL_CDROM_READ_Q_CHANNEL</a>. 


## -struct-fields




### -field Format

Specifies which subset of the Q data the read operation should return, as follows: 





#### IOCTL_CDROM_CURRENT_POSITION

Indicates that the read operation should return position information such as the track number, the index number, the absolute address, and the track relative address. If the IOCTL_CDROM_Q_CHANNEL device control IRP specifies this format, the information is returned in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_current_position">SUB_Q_CURRENT_POSITION</a> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_channel_data">SUB_Q_CHANNEL_DATA</a> structure.





#### IOCTL_CDROM_MEDIA_CATALOG

Indicates that the read operation should return the media catalog number. If the IOCTL_CDROM_Q_CHANNEL device control IRP specifies this format, the information is returned in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_media_catalog_number">SUB_Q_MEDIA_CATALOG_NUMBER</a> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_channel_data">SUB_Q_CHANNEL_DATA</a> structure.





#### IOCTL_CDROM_TRACK_ISRC

Indicates that the read operation should return the ISO/IEC 3901 Track International Standard Recording Code (ISRC). This code gives a unique number to an audio track. If the IOCTL_CDROM_Q_CHANNEL device control IRP specifies this format, the information is returned in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_track_isrc">SUB_Q_TRACK_ISRC</a> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_channel_data">SUB_Q_CHANNEL_DATA</a> structure.


### -field Track

Indicates the track number where the CD-ROM driver must read the Q subchannel data. If <b>Format</b> is set to IOCTL_CDROM_MEDIA_CATALOG, then the <b>Track</b> member must be set to zero.


## -remarks



The CDROM_SUB_Q_DATA_FORMAT structure indicates the track from which to read the Q part of the subchannel data and the format of the read.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_read_q_channel">IOCTL_CDROM_READ_Q_CHANNEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_channel_data">SUB_Q_CHANNEL_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_current_position">SUB_Q_CURRENT_POSITION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_media_catalog_number">SUB_Q_MEDIA_CATALOG_NUMBER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_track_isrc">SUB_Q_TRACK_ISRC</a>
 

 

