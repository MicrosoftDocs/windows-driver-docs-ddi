---
UID: NS:ntddcdrm._SUB_Q_MEDIA_CATALOG_NUMBER
title: _SUB_Q_MEDIA_CATALOG_NUMBER (ntddcdrm.h)
description: The SUB_Q_MEDIA_CATALOG_NUMBER structure contains position information and is used in conjunction with the SUB_Q_CHANNEL_DATA structure.
old-location: storage\sub_q_media_catalog_number.htm
tech.root: storage
ms.assetid: 14b0aed7-1602-41a3-bc55-59da40650860
ms.date: 03/29/2018
keywords: ["_SUB_Q_MEDIA_CATALOG_NUMBER structure"]
ms.keywords: "*PSUB_Q_MEDIA_CATALOG_NUMBER, PSUB_Q_MEDIA_CATALOG_NUMBER, PSUB_Q_MEDIA_CATALOG_NUMBER structure pointer [Storage Devices], SUB_Q_MEDIA_CATALOG_NUMBER, SUB_Q_MEDIA_CATALOG_NUMBER structure [Storage Devices], _SUB_Q_MEDIA_CATALOG_NUMBER, ntddcdrm/PSUB_Q_MEDIA_CATALOG_NUMBER, ntddcdrm/SUB_Q_MEDIA_CATALOG_NUMBER, storage.sub_q_media_catalog_number, structs-CD-ROM_d4acf54e-b837-4064-a654-4fa2ebbe7425.xml"
f1_keywords:
 - "ntddcdrm/SUB_Q_MEDIA_CATALOG_NUMBER"
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
- SUB_Q_MEDIA_CATALOG_NUMBER
product:
- Windows
targetos: Windows
req.typenames: SUB_Q_MEDIA_CATALOG_NUMBER, *PSUB_Q_MEDIA_CATALOG_NUMBER
---

# _SUB_Q_MEDIA_CATALOG_NUMBER structure


## -description


The SUB_Q_MEDIA_CATALOG_NUMBER structure contains position information and is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_channel_data">SUB_Q_CHANNEL_DATA</a> structure. 


## -struct-fields




### -field Header

Indicates, among other things, the length of the Q subchannel data that was retrieved. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_header">SUB_Q_HEADER</a> for further details. 


### -field FormatCode

Should have a value of IOCTL_CDROM_MEDIA_CATALOG. 


### -field Reserved

Reserved.


### -field Reserved1

Reserved.


### -field Mcval

Indicates that the media catalog number (MCN) data is valid if set to 1; set to zero otherwise.


### -field MediaCatalog

Contains the catalog number if <b>Mcval</b> is set to 1. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_sub_q_data_format">CDROM_SUB_Q_DATA_FORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_read_q_channel">IOCTL_CDROM_READ_Q_CHANNEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_channel_data">SUB_Q_CHANNEL_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_sub_q_header">SUB_Q_HEADER</a>
 

 

