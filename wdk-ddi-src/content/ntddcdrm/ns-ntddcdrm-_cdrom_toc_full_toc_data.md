---
UID: NS:ntddcdrm._CDROM_TOC_FULL_TOC_DATA
title: _CDROM_TOC_FULL_TOC_DATA (ntddcdrm.h)
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_FULL_TOC return their output data in this structure optionally followed by a series of descriptors of type CDROM_TOC_FULL_TOC_DATA_BLOCK.
old-location: storage\cdrom_toc_full_toc_data.htm
tech.root: storage
ms.assetid: c82e08e5-1450-40a3-a25a-49eefc7bc887
ms.date: 03/29/2018
ms.keywords: "*PCDROM_TOC_FULL_TOC_DATA, CDROM_TOC_FULL_TOC_DATA, CDROM_TOC_FULL_TOC_DATA structure [Storage Devices], PCDROM_TOC_FULL_TOC_DATA, PCDROM_TOC_FULL_TOC_DATA structure pointer [Storage Devices], _CDROM_TOC_FULL_TOC_DATA, ntddcdrm/CDROM_TOC_FULL_TOC_DATA, ntddcdrm/PCDROM_TOC_FULL_TOC_DATA, storage.cdrom_toc_full_toc_data, structs-CD-ROM_47099ab4-7dcb-4470-8350-8beea47587bd.xml"
ms.topic: struct
f1_keywords:
 - "ntddcdrm/CDROM_TOC_FULL_TOC_DATA"
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
- CDROM_TOC_FULL_TOC_DATA
product:
- Windows
targetos: Windows
req.typenames: CDROM_TOC_FULL_TOC_DATA, *PCDROM_TOC_FULL_TOC_DATA
---

# _CDROM_TOC_FULL_TOC_DATA structure


## -description


Device control IRPs with a control code of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_read_toc_ex">IOCTL_CDROM_READ_TOC_EX</a> and a format of CDROM_READ_TOC_EX_FORMAT_FULL_TOC return their output data in this structure optionally followed by a series of descriptors of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_toc_full_toc_data_block">CDROM_TOC_FULL_TOC_DATA_BLOCK</a>. 


## -struct-fields




### -field Length

Indicates the length, in bytes, of the table of contents data. This length value does not include the length of the <b>Length </b>member itself. 


### -field FirstCompleteSession

Contains the number of the first complete session. 


### -field LastCompleteSession

Contains the number of last complete session. 


### -field Descriptors

Contains zero or more track descriptors. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_toc_full_toc_data_block">CDROM_TOC_FULL_TOC_DATA_BLOCK</a> for a description of the track descriptor. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_read_toc_ex">CDROM_READ_TOC_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_toc_full_toc_data_block">CDROM_TOC_FULL_TOC_DATA_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_read_toc_ex">IOCTL_CDROM_READ_TOC_EX</a>
 

 

