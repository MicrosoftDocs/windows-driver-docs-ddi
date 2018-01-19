---
UID: NS:ntddcdrm._CDROM_TOC_CD_TEXT_DATA_BLOCK
title: _CDROM_TOC_CD_TEXT_DATA_BLOCK
author: windows-driver-content
description: This structure contains CD text descriptor data used in conjunction with the data in the CDROM_TOC_CD_TEXT_DATA structure.
old-location: storage\cdrom_toc_cd_text_data_block.htm
old-project: storage
ms.assetid: 119386fe-1eff-4dac-b9d5-54baefcf6e12
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _CDROM_TOC_CD_TEXT_DATA_BLOCK, CDROM_TOC_CD_TEXT_DATA_BLOCK, *PCDROM_TOC_CD_TEXT_DATA_BLOCK
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
req.alt-api: CDROM_TOC_CD_TEXT_DATA_BLOCK
req.alt-loc: ntddcdrm.h
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
req.typenames: CDROM_TOC_CD_TEXT_DATA_BLOCK, *PCDROM_TOC_CD_TEXT_DATA_BLOCK
---

# _CDROM_TOC_CD_TEXT_DATA_BLOCK structure



## -description
This structure contains CD text descriptor data used in conjunction with the data in the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_cd_text_data.md">CDROM_TOC_CD_TEXT_DATA</a> structure. 



## -syntax

````
typedef struct _CDROM_TOC_CD_TEXT_DATA_BLOCK {
  UCHAR PackType;
  UCHAR TrackNumber  :7;
  UCHAR ExtensionFlag  :1;
  UCHAR SequenceNumber;
  UCHAR CharacterPosition  :4;
  UCHAR BlockNumber  :3;
  UCHAR Unicode  :1;
  union {
    UCHAR Text[12];
    WCHAR WText[6];
  };
  UCHAR CRC[2];
} CDROM_TOC_CD_TEXT_DATA_BLOCK, *PCDROM_TOC_CD_TEXT_DATA_BLOCK;
````


## -struct-fields

### -field PackType

Indicates the type of pack data, as follows:




### -field CDROM_CD_TEXT_PACK_ALBUM_NAME 

Title of album or track. 

</dd>
</dl>



### -field CDROM_CD_TEXT_PACK_PERFORMER 

Names of the performers (in ASCII). 

</dd>
</dl>



### -field CDROM_CD_TEXT_PACK_SONGWRITER 

Names of the songwriters (in ASCII). 

</dd>
</dl>



### -field CDROM_CD_TEXT_PACK_COMPOSER 

Names of the composers (in ASCII). 

</dd>
</dl>



### -field CDROM_CD_TEXT_PACK_ARRANGER 

Names of the arrangers (in ASCII). 

</dd>
</dl>



### -field CDROM_CD_TEXT_PACK_MESSAGES 

Messages from content provider and/or artist (in ASCII). 

</dd>
</dl>



### -field CDROM_CD_TEXT_PACK_DISC_ID

Disc identification information. 

</dd>
</dl>



### -field CDROM_CD_TEXT_PACK_GENRE 

Genre identification and information. 

</dd>
</dl>



### -field CDROM_CD_TEXT_PACK_TOC_INFO 

Table of contents information. 

</dd>
</dl>



### -field CDROM_CD_TEXT_PACK_TOC_INFO2 

Second table of contents information. 

</dd>
</dl>



### -field CDROM_CD_TEXT_PACK_UPC_EAN 

UPC/EAN code of the album and ISRC code of each track. 

</dd>
</dl>



### -field CDROM_CD_TEXT_PACK_SIZE_INFO 

Size information for the block. 

</dd>
</dl>

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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_read_toc_ex.md">CDROM_READ_TOC_EX</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_cd_text_data.md">CDROM_TOC_CD_TEXT_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_TOC_CD_TEXT_DATA_BLOCK structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

