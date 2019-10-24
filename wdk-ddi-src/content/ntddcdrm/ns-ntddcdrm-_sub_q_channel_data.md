---
UID: NS:ntddcdrm._SUB_Q_CHANNEL_DATA
title: _SUB_Q_CHANNEL_DATA (ntddcdrm.h)
description: Device control IRPs with a control code of IOCTL_CDROM_READ_Q_CHANNEL return their output data in this union.
old-location: storage\sub_q_channel_data.htm
tech.root: storage
ms.assetid: d0304ac7-cb19-499c-81af-98be33312951
ms.date: 03/29/2018
ms.keywords: "*PSUB_Q_CHANNEL_DATA, PSUB_Q_CHANNEL_DATA, PSUB_Q_CHANNEL_DATA union pointer [Storage Devices], SUB_Q_CHANNEL_DATA, SUB_Q_CHANNEL_DATA union [Storage Devices], _SUB_Q_CHANNEL_DATA, ntddcdrm/PSUB_Q_CHANNEL_DATA, ntddcdrm/SUB_Q_CHANNEL_DATA, storage.sub_q_channel_data, structs-CD-ROM_f35761c8-b362-48eb-9cfa-6ee5e7232411.xml"
ms.topic: struct
f1_keywords:
 - "ntddcdrm/SUB_Q_CHANNEL_DATA"
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
- SUB_Q_CHANNEL_DATA
product:
- Windows
targetos: Windows
req.typenames: SUB_Q_CHANNEL_DATA, *PSUB_Q_CHANNEL_DATA
---

# _SUB_Q_CHANNEL_DATA structure


## -description


Device control IRPs with a control code of IOCTL_CDROM_READ_Q_CHANNEL return their output data in this union. 


## -struct-fields




### -field CurrentPosition

Contains position information, such as the absolute and relative addresses, in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_current_position">SUB_Q_CURRENT_POSITION</a> structure. 


### -field MediaCatalog

Contains the media catalog number in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_media_catalog_number">SUB_Q_MEDIA_CATALOG_NUMBER</a>  structure.


### -field TrackIsrc

Contains the TrackIsrc code in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_track_isrc">SUB_Q_TRACK_ISRC</a> structure. 


## -remarks



The value of the <b>Format </b>member of the CDROM_SUB_Q_DATA_FORMAT structure that is passed as input with IOCTL_CDROM_READ_Q_CHANNEL determines which member of this union is used to return the output data. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_sub_q_data_format">CDROM_SUB_Q_DATA_FORMAT</a> for a detailed explanation. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_sub_q_data_format">CDROM_SUB_Q_DATA_FORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_read_q_channel">IOCTL_CDROM_READ_Q_CHANNEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_current_position">SUB_Q_CURRENT_POSITION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_media_catalog_number">SUB_Q_MEDIA_CATALOG_NUMBER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_track_isrc">SUB_Q_TRACK_ISRC</a>
 

 

