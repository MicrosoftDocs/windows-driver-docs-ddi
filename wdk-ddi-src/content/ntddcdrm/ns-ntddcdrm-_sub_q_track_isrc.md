---
UID: NS:ntddcdrm._SUB_Q_TRACK_ISRC
title: "_SUB_Q_TRACK_ISRC"
author: windows-driver-content
description: The SUB_Q_TRACK_ISC contains position information and is used in conjunction with the SUB_Q_CHANNEL_DATA structure.
old-location: storage\sub_q_track_isrc.htm
old-project: storage
ms.assetid: 0439bd46-b009-435d-aab7-efca48a17cb7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.sub_q_track_isrc, structs-CD-ROM_372ebccd-64cd-4f5d-a59c-de75c5ffe112.xml, _SUB_Q_TRACK_ISRC, PSUB_Q_TRACK_ISRC structure pointer [Storage Devices], ntddcdrm/SUB_Q_TRACK_ISRC, SUB_Q_TRACK_ISRC structure [Storage Devices], ntddcdrm/PSUB_Q_TRACK_ISRC, PSUB_Q_TRACK_ISRC, *PSUB_Q_TRACK_ISRC, SUB_Q_TRACK_ISRC
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
-	SUB_Q_TRACK_ISRC
product: Windows
targetos: Windows
req.typenames: "*PSUB_Q_TRACK_ISRC, SUB_Q_TRACK_ISRC"
---

# _SUB_Q_TRACK_ISRC structure


## -description


The SUB_Q_TRACK_ISC contains position information and is used in conjunction with the <a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_channel_data.md">SUB_Q_CHANNEL_DATA</a> structure. 


## -syntax


````
typedef struct _SUB_Q_TRACK_ISRC {
  SUB_Q_HEADER Header;
  UCHAR        FormatCode;
  UCHAR        Reserved0;
  UCHAR        Track;
  UCHAR        Reserved1;
  UCHAR        Reserved2  :7;
  UCHAR        Tcval  :1;
  UCHAR        TrackIsrc[15];
} SUB_Q_TRACK_ISRC, *PSUB_Q_TRACK_ISRC;
````


## -struct-fields




### -field Header

Indicates, among other things, the length of the Q subchannel data that was retrieved. See <a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_header.md">SUB_Q_HEADER</a> for further details. 


### -field FormatCode

Should have a value of IOCTL_CDROM_TRACK_ISRC. 


### -field Reserved0

Reserved. 


### -field Track

Contains the number for the track for which the ISRC value was requested. 


### -field Reserved1

Reserved. 


### -field Reserved2

Reserved. 


### -field Tcval

Indicates that ISRC data was detected, if set to 1. Otherwise, if set to zero, indicates that <b>TrackIsrc</b> is invalid. 


### -field TrackIsrc

Contains an array that holds the tracking ISRC data. 


## -see-also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_q_channel.md">IOCTL_CDROM_READ_Q_CHANNEL</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_channel_data.md">SUB_Q_CHANNEL_DATA</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_sub_q_data_format.md">CDROM_SUB_Q_DATA_FORMAT</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_header.md">SUB_Q_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SUB_Q_TRACK_ISRC structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

