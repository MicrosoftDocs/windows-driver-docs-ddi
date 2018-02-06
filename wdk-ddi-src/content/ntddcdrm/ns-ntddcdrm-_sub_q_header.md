---
UID: NS:ntddcdrm._SUB_Q_HEADER
title: "_SUB_Q_HEADER"
author: windows-driver-content
description: The SUB_Q_HEADER structure contains audio status information and the length of the Q subchannel data being returned. This structure is used in conjunction with SUB_Q_CHANNEL_DATA.
old-location: storage\sub_q_header.htm
old-project: storage
ms.assetid: 3ee3657d-acdd-4d3f-9cff-eb4a494429b4
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSUB_Q_HEADER structure pointer [Storage Devices], _SUB_Q_HEADER, *PSUB_Q_HEADER, storage.sub_q_header, PSUB_Q_HEADER, ntddcdrm/SUB_Q_HEADER, ntddcdrm/PSUB_Q_HEADER, structs-CD-ROM_c72df573-2396-4bf3-b586-7241d408c550.xml, SUB_Q_HEADER, SUB_Q_HEADER structure [Storage Devices]
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
-	SUB_Q_HEADER
product: Windows
targetos: Windows
req.typenames: "*PSUB_Q_HEADER, SUB_Q_HEADER"
---

# _SUB_Q_HEADER structure


## -description


The SUB_Q_HEADER structure contains audio status information and the length of the Q subchannel data being returned. This structure is used in conjunction with <a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_channel_data.md">SUB_Q_CHANNEL_DATA</a>.


## -syntax


````
typedef struct _SUB_Q_HEADER {
  UCHAR Reserved;
  UCHAR AudioStatus;
  UCHAR DataLength[2];
} SUB_Q_HEADER, *PSUB_Q_HEADER;
````


## -struct-fields




### -field Reserved

Reserved.


### -field AudioStatus

Reports the audio status with one of the following flags:














#### AUDIO_STATUS_NOT_SUPPORTED

Audio status byte not supported or not valid.


#### AUDIO_STATUS_IN_PROGRESS

Audio play operation is in progress.


#### AUDIO_STATUS_PAUSED

Audio play operation is paused.


#### AUDIO_STATUS_PLAY_COMPLETE

Audio play operation completed successfully.


#### AUDIO_STATUS_PLAY_ERROR

Audio play operation stopped due to error.


#### AUDIO_STATUS_NO_STATUS

No current audio status to return.


### -field DataLength

Gives the length of Q subchannel data that follows this header structure. The bytes in this array are arranged in big-endian order. <b>DataLength</b>[0] contains the most significant byte, and <b>DataLength</b>[1] contains the least significant byte. 


## -see-also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_q_channel.md">IOCTL_CDROM_READ_Q_CHANNEL</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_channel_data.md">SUB_Q_CHANNEL_DATA</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_sub_q_data_format.md">CDROM_SUB_Q_DATA_FORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SUB_Q_HEADER structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

