---
UID: NS:ntddcdrm._SUB_Q_HEADER
title: _SUB_Q_HEADER (ntddcdrm.h)
description: The SUB_Q_HEADER structure contains audio status information and the length of the Q subchannel data being returned. This structure is used in conjunction with SUB_Q_CHANNEL_DATA.
old-location: storage\sub_q_header.htm
tech.root: storage
ms.assetid: 3ee3657d-acdd-4d3f-9cff-eb4a494429b4
ms.date: 03/29/2018
ms.keywords: "*PSUB_Q_HEADER, PSUB_Q_HEADER, PSUB_Q_HEADER structure pointer [Storage Devices], SUB_Q_HEADER, SUB_Q_HEADER structure [Storage Devices], _SUB_Q_HEADER, ntddcdrm/PSUB_Q_HEADER, ntddcdrm/SUB_Q_HEADER, storage.sub_q_header, structs-CD-ROM_c72df573-2396-4bf3-b586-7241d408c550.xml"
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
-	SUB_Q_HEADER
product:
- Windows
targetos: Windows
req.typenames: SUB_Q_HEADER, *PSUB_Q_HEADER
---

# _SUB_Q_HEADER structure


## -description


The SUB_Q_HEADER structure contains audio status information and the length of the Q subchannel data being returned. This structure is used in conjunction with <a href="https://msdn.microsoft.com/library/windows/hardware/ff567595">SUB_Q_CHANNEL_DATA</a>.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551371">CDROM_SUB_Q_DATA_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559363">IOCTL_CDROM_READ_Q_CHANNEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567595">SUB_Q_CHANNEL_DATA</a>
 

 

