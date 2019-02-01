---
UID: NS:ntddcdrm._CDROM_TOC_FULL_TOC_DATA_BLOCK
title: _CDROM_TOC_FULL_TOC_DATA_BLOCK (ntddcdrm.h)
description: The CDROM_TOC_FULL_TOC_DATA_BLOCK structure contains track descriptor data used in conjunction with the data from the CDROM_TOC_FULL_TOC_DATA structure.
old-location: storage\cdrom_toc_full_toc_data_block.htm
tech.root: storage
ms.assetid: 8d6d1283-b64e-4c3b-8a45-376cfe76a19d
ms.date: 03/29/2018
ms.keywords: "*PCDROM_TOC_FULL_TOC_DATA_BLOCK, CDROM_TOC_FULL_TOC_DATA_BLOCK, CDROM_TOC_FULL_TOC_DATA_BLOCK structure [Storage Devices], PCDROM_TOC_FULL_TOC_DATA_BLOCK, PCDROM_TOC_FULL_TOC_DATA_BLOCK structure pointer [Storage Devices], _CDROM_TOC_FULL_TOC_DATA_BLOCK, ntddcdrm/CDROM_TOC_FULL_TOC_DATA_BLOCK, ntddcdrm/PCDROM_TOC_FULL_TOC_DATA_BLOCK, storage.cdrom_toc_full_toc_data_block, structs-CD-ROM_c55aee22-f6ca-4567-82c6-7bb960f4976a.xml"
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
-	CDROM_TOC_FULL_TOC_DATA_BLOCK
product:
- Windows
targetos: Windows
req.typenames: CDROM_TOC_FULL_TOC_DATA_BLOCK, *PCDROM_TOC_FULL_TOC_DATA_BLOCK
---

# _CDROM_TOC_FULL_TOC_DATA_BLOCK structure


## -description


The CDROM_TOC_FULL_TOC_DATA_BLOCK structure contains track descriptor data used in conjunction with the data from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551383">CDROM_TOC_FULL_TOC_DATA</a> structure. 


## -struct-fields




### -field SessionNumber

Contains the number of the session that the track belongs to. 


### -field Control

Indicates the attributes of the track. 





#### AUDIO_WITH_PREEMPHASIS

Indicates two audio channels with preemphasis of 50/15 microseconds have been added. 





#### DIGITAL_COPY_PERMITTED

Indicates digital copying is allowed. 





#### AUDIO_DATA_TRACK

Indicates that the track contains nonaudio data. 





#### TWO_FOUR_CHANNEL_AUDIO

Indicates that the track contains four channels of audio data.


### -field Adr

Indicates the type of information encoded in the Q subchannel of the block where this table of contents entry was found.





#### ADR_NO_MODE_INFORMATION

Q subchannel mode information not supplied. 





#### ADR_ENCODES_CURRENT_POSITION



##### Q subchannel encodes current position data



###### 





#### ADR_ENCODES_MEDIA_CATALOG

Q subchannel encodes media catalog number. 





#### ADR_ENCODES_ISRC

Q subchannel encodes ISRC. 


### -field Reserved1

Reserved. 


### -field Point

Defines various types of information within the table of contents lead-in area. For information about the permissible values for this member, see specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS).


### -field MsfExtra

See specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS) For information about the permissible values for this member. 


### -field Zero

Contains the value of the zero bit.


### -field Msf

Contains the minute, second, and frame. Msf[0] contains the minutes field. Msf[1] contains the seconds field, and Msf[2] contains the frames field. MSF is a format similar to logical block addressing. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551366">CDROM_READ_TOC_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551383">CDROM_TOC_FULL_TOC_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559367">IOCTL_CDROM_READ_TOC_EX</a>
 

 

