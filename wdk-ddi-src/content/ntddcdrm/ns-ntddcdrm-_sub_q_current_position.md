---
UID: NS:ntddcdrm._SUB_Q_CURRENT_POSITION
title: "_SUB_Q_CURRENT_POSITION"
author: windows-driver-content
description: The SUB_Q_CURRENT_POSITION structure contains position information and is used in conjunction with SUB_Q_CHANNEL_DATA.
old-location: storage\sub_q_current_position.htm
old-project: storage
ms.assetid: 816baec4-3dd0-4025-ba34-035bf6f241d3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSUB_Q_CURRENT_POSITION, PSUB_Q_CURRENT_POSITION, PSUB_Q_CURRENT_POSITION structure pointer [Storage Devices], SUB_Q_CURRENT_POSITION, SUB_Q_CURRENT_POSITION structure [Storage Devices], _SUB_Q_CURRENT_POSITION, ntddcdrm/PSUB_Q_CURRENT_POSITION, ntddcdrm/SUB_Q_CURRENT_POSITION, storage.sub_q_current_position, structs-CD-ROM_f9833ad0-bb9c-418e-8e98-2c2f790a0e7e.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddcdrm.h
api_name:
-	SUB_Q_CURRENT_POSITION
product:
- Windows
targetos: Windows
req.typenames: SUB_Q_CURRENT_POSITION, *PSUB_Q_CURRENT_POSITION
---

# _SUB_Q_CURRENT_POSITION structure


## -description


The SUB_Q_CURRENT_POSITION structure contains position information and is used in conjunction with <a href="https://msdn.microsoft.com/library/windows/hardware/ff567595">SUB_Q_CHANNEL_DATA</a>. 


## -struct-fields




### -field Header

Indicates, among other things, the length of the Q subchannel data that was retrieved. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff567598">SUB_Q_HEADER</a> for more details. 


### -field FormatCode

Should have a value of IOCTL_CDROM_CURRENT_POSITION. 


### -field Control

Defines various types of information within the table of contents lead-in area. For more information about the permissible values for this member, see specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS). 


### -field ADR

Indicates the type of information encoded in the Q subchannel of the block. For information about the permissible values for this member, see specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS). 


### -field TrackNumber

Contains the current track number.


### -field IndexNumber

Contains the current index number.


### -field AbsoluteAddress

Gives the current location relative to the logical beginning of the media. The bytes in this array are arranged in big-endian order. <b>AbsoluteAddress</b>[0] contains the most significant byte, and <b>AbsoluteAddress</b>[3] contains the least significant byte. 


### -field TrackRelativeAddress

Gives the current location relative to the logical beginning of the current track. The bytes in this array are arranged in big-endian order. <b>TrackRelativeAddress</b>[0] contains the most significant byte, and <b>TrackRelativeAddress</b>[3] contains the least significant byte. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551371">CDROM_SUB_Q_DATA_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559363">IOCTL_CDROM_READ_Q_CHANNEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567595">SUB_Q_CHANNEL_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567598">SUB_Q_HEADER</a>
 

 

