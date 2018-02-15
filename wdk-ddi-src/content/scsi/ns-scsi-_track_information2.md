---
UID: NS:scsi._TRACK_INFORMATION2
title: "_TRACK_INFORMATION2"
author: windows-driver-content
description: The TRACK_INFORMATION2 structure is used to report track information.
old-location: storage\track_information2.htm
old-project: storage
ms.assetid: 2fea2f8a-eb55-409c-80d2-c3f49ab6bfdf
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.track_information2, TRACK_INFORMATION2, scsi/TRACK_INFORMATION2, PTRACK_INFORMATION2 structure pointer [Storage Devices], structs-CD-ROM_a77c4142-fe27-489b-ab9c-1637cf4b911d.xml, scsi/PTRACK_INFORMATION2, PTRACK_INFORMATION2, _TRACK_INFORMATION2, TRACK_INFORMATION2 structure [Storage Devices], *PTRACK_INFORMATION2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsi.h
req.include-header: Scsi.h
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
-	scsi.h
apiname:
-	TRACK_INFORMATION2
product: Windows
targetos: Windows
req.typenames: TRACK_INFORMATION2, *PTRACK_INFORMATION2
req.product: Windows 10 or later.
---

# _TRACK_INFORMATION2 structure


## -description


The TRACK_INFORMATION2 structure is used to report track information.


## -syntax


````
typedef struct _TRACK_INFORMATION2 {
  UCHAR Length[2];
  UCHAR TrackNumberLsb;
  UCHAR SessionNumberLsb;
  UCHAR Reserved4;
  UCHAR TrackMode  :4;
  UCHAR Copy  :1;
  UCHAR Damage  :1;
  UCHAR Reserved5  :2;
  UCHAR DataMode  :4;
  UCHAR FixedPacket  :1;
  UCHAR Packet  :1;
  UCHAR Blank  :1;
  UCHAR ReservedTrack  :1;
  UCHAR NWA_V  :1;
  UCHAR LRA_V  :1;
  UCHAR Reserved6  :6;
  UCHAR TrackStartAddress[4];
  UCHAR NextWritableAddress[4];
  UCHAR FreeBlocks[4];
  UCHAR FixedPacketSize[4];
  UCHAR TrackSize[4];
  UCHAR LastRecordedAddress[4];
  UCHAR TrackNumberMsb;
  UCHAR SessionNumberMsb;
  UCHAR Reserved7[2];
} TRACK_INFORMATION2, *PTRACK_INFORMATION2;
````


## -struct-fields




### -field Length

The length, in bytes, of this structure.


### -field TrackNumberLsb

The least significant byte of the track number.


### -field SessionNumberLsb

The least significant byte of the session number.


### -field Reserved4

Reserved.


### -field TrackMode

The track mode. See the <i>SCSI-3 Multi-Media </i>specification for an explanation of meaning of this member.


### -field Copy

The copy bit indicates whether the track is a copy or not. If this bit is 1, the track is a copy. If it is 0, the track is not a copy.


### -field Damage

The damage bit indicates, together with the NWA_V bit, whether a write to the media is complete or not, and what sort of methods the CD-ROM class driver can use to complete the write. See the <i>SCSI-3 Multi-Media </i>specification for an explanation of how to interpret the values in the <b>Damage</b> and <b>NWA_V</b> members.


### -field Reserved5

Reserved.


### -field DataMode

The data mode. This member can have any of the following values:

<table>
<tr>
<td>
<b>Value</b>

</td>
<td>
<b>Meaning</b>

</td>
</tr>
<tr>
<td>
0x1

</td>
<td>
The track uses data mode 1 (ISO/IEC 10149)

</td>
</tr>
<tr>
<td>
0x2

</td>
<td>
The track uses data mode 2 (ISO/IEC 10149 or CD-ROM XA)

</td>
</tr>
<tr>
<td>
0xf

</td>
<td>
There is no track descriptor block, and therefore the data block type of the track is unknown.

</td>
</tr>
</table>
 


### -field FixedPacket

The fixed packet bit indicates, under some circumstances, when set to 1, that write operations to the track must must use fixed packets. For a complete explanation of the meaning of this bit, see the <i>SCSI Multimedia Commands - 3 (MMC-3)</i> specification.


### -field Packet

The fixed packet bit indicates, under some circumstances, when set to 1, that write operations to the track must must use fixed packets. For a complete explanation of the meaning of this bit, see the <i>SCSI Multimedia Commands - 3 (MMC-3)</i> specification.


### -field Blank

The blank bit, when set to 1, indicates that the track contains no written data and last recorded address field is invalid. For a complete explanation of the meaning of this bit, see the <i>SCSI Multimedia Commands - 3 (MMC-3)</i> specification.


### -field ReservedTrack

The reserved track bit, when 1, indicates that the track is reserved.


### -field NWA_V

A boolean value that indicates, when 1, that the value in <b>NextWritableAddress</b> is valid. If 0, the value in <b>NextWritableAddress</b> is invalid.


### -field LRA_V

A boolean value that indicates whether the <b>LastRecordedAddress</b> member is valid or not. If <b>LRA_V</b> is 1, the <b>LastRecordedAddress</b> member is valid. If 0, the <b>LastRecordedAddress</b> member is not valid.


### -field Reserved6

Reserved.


### -field TrackStartAddress

The starting address of the specified track.


### -field NextWritableAddress

The logical block address of the next writable user block in the track specified by the track number (<b>TrackNumberLsb</b> and <b>TrackNumberMsb</b>).


### -field FreeBlocks

The maximum number of user data blocks that are available for recording in the track.


### -field FixedPacketSize

The blocking factor. This value The fixed packet size is valid only when the Packet and the FP bits are both set to one.


### -field TrackSize

Track Size is the number of user data blocks in the track.


### -field LastRecordedAddress


### -field TrackNumberMsb

The most significant byte of the track number.


### -field SessionNumberMsb

The most significant byte of the session number.


### -field Reserved7

Reserved7

