---
UID: NS:ntddcdrm._CDROM_TOC_CD_TEXT_DATA_BLOCK
title: "_CDROM_TOC_CD_TEXT_DATA_BLOCK"
description: This structure contains CD text descriptor data used in conjunction with the data in the CDROM_TOC_CD_TEXT_DATA structure.
old-location: storage\cdrom_toc_cd_text_data_block.htm
tech.root: storage
ms.assetid: 119386fe-1eff-4dac-b9d5-54baefcf6e12
ms.date: 03/29/2018
ms.keywords: "*PCDROM_TOC_CD_TEXT_DATA_BLOCK, CDROM_TOC_CD_TEXT_DATA_BLOCK, CDROM_TOC_CD_TEXT_DATA_BLOCK structure [Storage Devices], PCDROM_TOC_CD_TEXT_DATA_BLOCK, PCDROM_TOC_CD_TEXT_DATA_BLOCK structure pointer [Storage Devices], _CDROM_TOC_CD_TEXT_DATA_BLOCK, ntddcdrm/CDROM_TOC_CD_TEXT_DATA_BLOCK, ntddcdrm/PCDROM_TOC_CD_TEXT_DATA_BLOCK, storage.cdrom_toc_cd_text_data_block, structs-CD-ROM_6bdb8d21-6388-4505-b9a1-1b3e1e594e02.xml"
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
-	CDROM_TOC_CD_TEXT_DATA_BLOCK
product:
- Windows
targetos: Windows
req.typenames: CDROM_TOC_CD_TEXT_DATA_BLOCK, *PCDROM_TOC_CD_TEXT_DATA_BLOCK
---

# _CDROM_TOC_CD_TEXT_DATA_BLOCK structure


## -description


This structure contains CD text descriptor data used in conjunction with the data in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551380">CDROM_TOC_CD_TEXT_DATA</a> structure. 


## -struct-fields




### -field PackType

Indicates the type of pack data, as follows:





#### CDROM_CD_TEXT_PACK_ALBUM_NAME

Title of album or track. 





#### CDROM_CD_TEXT_PACK_PERFORMER

Names of the performers (in ASCII). 





#### CDROM_CD_TEXT_PACK_SONGWRITER

Names of the songwriters (in ASCII). 





#### CDROM_CD_TEXT_PACK_COMPOSER

Names of the composers (in ASCII). 





#### CDROM_CD_TEXT_PACK_ARRANGER

Names of the arrangers (in ASCII). 





#### CDROM_CD_TEXT_PACK_MESSAGES

Messages from content provider and/or artist (in ASCII). 





#### CDROM_CD_TEXT_PACK_DISC_ID

Disc identification information. 





#### CDROM_CD_TEXT_PACK_GENRE

Genre identification and information. 





#### CDROM_CD_TEXT_PACK_TOC_INFO

Table of contents information. 





#### CDROM_CD_TEXT_PACK_TOC_INFO2

Second table of contents information. 





#### CDROM_CD_TEXT_PACK_UPC_EAN

UPC/EAN code of the album and ISRC code of each track. 





#### CDROM_CD_TEXT_PACK_SIZE_INFO

Size information for the block. 


### -field TrackNumber

See specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS) For information about the permissible values for this member. 


### -field ExtensionFlag

Must be set to zero. 


### -field SequenceNumber

See specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS) For information about the permissible values for this member. 


### -field CharacterPosition

See specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS) For information about the permissible values for this member. 


### -field BlockNumber

See specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS) For information about the permissible values for this member.  


### -field Unicode

Indicates, when set to 1, that the text is stored in Unicode format. 


### -field Text

Contains text descriptor data in the form of 8-bit ASCII characters.


### -field WText

Contains text descriptor data in the form of 16-bit (wide) characters.


### -field CRC

Contains the cyclic redundancy check.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551366">CDROM_READ_TOC_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551380">CDROM_TOC_CD_TEXT_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559367">IOCTL_CDROM_READ_TOC_EX</a>
 

 

