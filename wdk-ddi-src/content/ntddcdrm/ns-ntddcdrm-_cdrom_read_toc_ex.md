---
UID: NS:ntddcdrm._CDROM_READ_TOC_EX
title: "_CDROM_READ_TOC_EX"
author: windows-driver-content
description: When drivers query a target CD-ROM device with IOCTL_CDROM_READ_TOC_EX they must define the query with this structure.
old-location: storage\cdrom_read_toc_ex.htm
old-project: storage
ms.assetid: 17dbc843-dc65-40d7-9cda-916127e4cfa4
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: structs-CD-ROM_b12c5d5a-b319-4122-be7f-721bd384dbf2.xml, _CDROM_READ_TOC_EX, PCDROM_READ_TOC_EX, CDROM_READ_TOC_EX structure [Storage Devices], storage.cdrom_read_toc_ex, ntddcdrm/CDROM_READ_TOC_EX, CDROM_READ_TOC_EX, ntddcdrm/PCDROM_READ_TOC_EX, PCDROM_READ_TOC_EX structure pointer [Storage Devices], *PCDROM_READ_TOC_EX
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
-	CDROM_READ_TOC_EX
product: Windows
targetos: Windows
req.typenames: "*PCDROM_READ_TOC_EX, CDROM_READ_TOC_EX"
---

# _CDROM_READ_TOC_EX structure


## -description


When drivers query a target CD-ROM device with <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a> they must define the query with this structure. 


## -syntax


````
typedef struct _CDROM_READ_TOC_EX {
  UCHAR Format  :4;
  UCHAR Reserved1  :3;
  UCHAR Msf  :1;
  UCHAR SessionTrack;
  UCHAR Reserved2;
  UCHAR Reserved3;
} CDROM_READ_TOC_EX, *PCDROM_READ_TOC_EX;
````


## -struct-fields




### -field Format

Specifies table of contents read operation, as follows:





#### CDROM_READ_TOC_EX_FORMAT_TOC

Query the device for the table of contents for the specified session(s). The <b>SessionTrack</b> member of the structure specifies the starting track number of the session for which the data will be returned. For multisession CD-ROMs, this command will return the table of contents data for all sessions. For track number 0xAA, it returns the lead-out area of the last complete session. The output data is reported in a <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc.md">CDROM_TOC</a> structure.





#### CDROM_READ_TOC_EX_FORMAT_SESSION

Query the device for the first complete session number, the last complete session number, and the last complete session starting address. The output data is reported in a <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_session_data.md">CDROM_TOC_SESSION_DATA</a> structure. With this format, the <b>SessionTrack</b> member is reserved and must be set to zero. This format provides the initiator with quick access to the last finalized session starting address. 





#### CDROM_READ_TOC_EX_FORMAT_FULL_TOC

Query the device for all Q subcode data in the lead-in table of contents areas starting from the session number specified in the <b>SessionTrack</b> member. The output data is reported in a header structure, <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_full_toc_data.md">CDROM_TOC_FULL_TOC_DATA</a>, followed by a series of track descriptors defined in <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_full_toc_data_block.md">CDROM_TOC_FULL_TOC_DATA_BLOCK</a>. In this format, logical block addressing (LBA) is not defined, and the <b>Msf</b> member must be set to 1.





#### CDROM_READ_TOC_EX_FORMAT_PMA

Query the device for all Q subcode data in the <i>program memory area</i> (PMA). The output data is reported in a <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_pma_data.md">CDROM_TOC_PMA_DATA</a> structure. In this format, the <b>SessionTrack</b> member is reserved and must be set to zero. Logical block addressing (LBA) is not defined, and the <b>Msf</b> member must be set to 1.





#### CDROM_READ_TOC_EX_FORMAT_ATIP

Query the device for <i>absolute time in pregroove</i> (ATIP) data. The output data is reported in the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_atip_data.md">CDROM_TOC_ATIP_DATA</a> structure. In this format, the <b>SessionTrack</b> member is reserved and must be set to zero. Logical block addressing (LBA) is not defined, and the <b>Msf</b> member must be set to 1.





#### CDROM_READ_TOC_EX_FORMAT_CDTEXT

Query the device for CD-TEXT information that is recorded in the lead-in area as R-W subchannel data. The output data is reported in a <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_cd_text_data.md">CDROM_TOC_CD_TEXT_DATA</a> structure with an appended array of <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_cd_text_data_block.md">CDROM_TOC_CD_TEXT_DATA_BLOCK</a> structures.


### -field Reserved1

Reserved. 


### -field Msf

Indicates the minute-second-frame bit. When set to one, this bit indicates that minute-second-frame (MSF) addressing must be used. When zero, it indicates that logical block addressing (LBA) must be used. 


### -field SessionTrack

Specifies the starting track number for which the data will be returned, the session for which the command is targeted, or a reserved field that drivers should set to zero. Which of these values <b>SessionTrack</b> takes depends on the value of the <b>Format</b> member. 


### -field Reserved2

Reserved


### -field Reserved3

Reserved


## -remarks



For further information and definitions of terms used in this reference page and in the reference pages of related structures, see specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS).




## -see-also

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_atip_data.md">CDROM_TOC_ATIP_DATA</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_cd_text_data_block.md">CDROM_TOC_CD_TEXT_DATA_BLOCK</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc.md">CDROM_TOC</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_full_toc_data.md">CDROM_TOC_FULL_TOC_DATA</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_session_data.md">CDROM_TOC_SESSION_DATA</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_pma_data.md">CDROM_TOC_PMA_DATA</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_full_toc_data_block.md">CDROM_TOC_FULL_TOC_DATA_BLOCK</a>



<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_cd_text_data.md">CDROM_TOC_CD_TEXT_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_READ_TOC_EX structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

