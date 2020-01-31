---
UID: NS:ntddcdrm._CDROM_TOC_ATIP_DATA
title: _CDROM_TOC_ATIP_DATA (ntddcdrm.h)
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_ATIP return their output data in this header structure followed by a series of descriptors of type CDROM_TOC_ATIP_DATA_BLOCK.
old-location: storage\cdrom_toc_atip_data.htm
tech.root: storage
ms.assetid: 4caf59d4-262a-49e3-8b66-9cf29ed5cee5
ms.date: 03/29/2018
ms.keywords: "*PCDROM_TOC_ATIP_DATA, CDROM_TOC_ATIP_DATA, CDROM_TOC_ATIP_DATA structure [Storage Devices], PCDROM_TOC_ATIP_DATA, PCDROM_TOC_ATIP_DATA structure pointer [Storage Devices], _CDROM_TOC_ATIP_DATA, ntddcdrm/CDROM_TOC_ATIP_DATA, ntddcdrm/PCDROM_TOC_ATIP_DATA, storage.cdrom_toc_atip_data, structs-CD-ROM_57534148-0c2f-4182-8b0e-3fe4ed10505e.xml"
f1_keywords:
 - "ntddcdrm/CDROM_TOC_ATIP_DATA"
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
- CDROM_TOC_ATIP_DATA
product:
- Windows
targetos: Windows
req.typenames: CDROM_TOC_ATIP_DATA, *PCDROM_TOC_ATIP_DATA
---

# _CDROM_TOC_ATIP_DATA structure


## -description


Device control IRPs with a control code of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_read_toc_ex">IOCTL_CDROM_READ_TOC_EX</a> and a format of CDROM_READ_TOC_EX_FORMAT_ATIP return their output data in this header structure followed by a series of descriptors of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_toc_atip_data_block">CDROM_TOC_ATIP_DATA_BLOCK</a>.


## -struct-fields




### -field Length

Indicates the number of bytes to be transferred in response to the command. This length value does not include the length of the <b>Length </b>member itself. 


### -field Reserved1

Reserved. 


### -field Reserved2

Reserved. 


### -field Descriptors

Contains zero or more ATIP data block descriptors of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_toc_atip_data_block">CDROM_TOC_ATIP_DATA_BLOCK</a>. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_read_toc_ex">CDROM_READ_TOC_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_toc_atip_data_block">CDROM_TOC_ATIP_DATA_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_read_toc_ex">IOCTL_CDROM_READ_TOC_EX</a>
 

 

