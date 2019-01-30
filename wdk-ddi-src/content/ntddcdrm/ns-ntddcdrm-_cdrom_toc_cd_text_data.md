---
UID: NS:ntddcdrm._CDROM_TOC_CD_TEXT_DATA
title: "_CDROM_TOC_CD_TEXT_DATA" (ntddcdrm.h)
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_CDTEXT return their output data in this structure followed by a series of descriptors of type CDROM_TOC_CD_TEXT_DATA_BLOCK.
old-location: storage\cdrom_toc_cd_text_data.htm
tech.root: storage
ms.assetid: 92e87c1d-17c4-4ac8-af9d-08863ce84c9e
ms.date: 03/29/2018
ms.keywords: "*PCDROM_TOC_CD_TEXT_DATA, CDROM_TOC_CD_TEXT_DATA, CDROM_TOC_CD_TEXT_DATA structure [Storage Devices], PCDROM_TOC_CD_TEXT_DATA, PCDROM_TOC_CD_TEXT_DATA structure pointer [Storage Devices], _CDROM_TOC_CD_TEXT_DATA, ntddcdrm/CDROM_TOC_CD_TEXT_DATA, ntddcdrm/PCDROM_TOC_CD_TEXT_DATA, storage.cdrom_toc_cd_text_data, structs-CD-ROM_7c78a819-dd2b-45bf-ba44-b8115fe1b998.xml"
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
-	CDROM_TOC_CD_TEXT_DATA
product:
- Windows
targetos: Windows
req.typenames: CDROM_TOC_CD_TEXT_DATA, *PCDROM_TOC_CD_TEXT_DATA
---

# _CDROM_TOC_CD_TEXT_DATA structure


## -description


Device control IRPs with a control code of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559367">IOCTL_CDROM_READ_TOC_EX</a> and a format of CDROM_READ_TOC_EX_FORMAT_CDTEXT return their output data in this structure followed by a series of descriptors of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551382">CDROM_TOC_CD_TEXT_DATA_BLOCK</a>. 


## -struct-fields




### -field Length

Indicates the number of bytes to be transferred in response to the IOCTL_CDROM_READ_TOC_EX IOCTL. This length value does not include the length of the <b>Length </b>member itself. 


### -field Reserved1

Reserved.


### -field Reserved2

Reserved.


### -field Descriptors

Contains zero or more text data block descriptors of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551382">CDROM_TOC_CD_TEXT_DATA_BLOCK</a>. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551366">CDROM_READ_TOC_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551382">CDROM_TOC_CD_TEXT_DATA_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559367">IOCTL_CDROM_READ_TOC_EX</a>
 

 

