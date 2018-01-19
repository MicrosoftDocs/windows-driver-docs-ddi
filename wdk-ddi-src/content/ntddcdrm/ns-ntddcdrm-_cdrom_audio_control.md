---
UID: NS:ntddcdrm._CDROM_AUDIO_CONTROL
title: _CDROM_AUDIO_CONTROL
author: windows-driver-content
description: The CDROM_AUDIO_CONTROL structure is used in conjunction with the IOCTL_CDROM_GET_CONTROL request to report the audio playback mode.
old-location: storage\cdrom_audio_control.htm
old-project: storage
ms.assetid: f99ad24d-e1cf-4381-93b9-c10e4b19b401
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _CDROM_AUDIO_CONTROL, CDROM_AUDIO_CONTROL, *PCDROM_AUDIO_CONTROL
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
req.alt-api: CDROM_AUDIO_CONTROL
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
req.typenames: CDROM_AUDIO_CONTROL, *PCDROM_AUDIO_CONTROL
---

# _CDROM_AUDIO_CONTROL structure



## -description
The CDROM_AUDIO_CONTROL structure is used in conjunction with the IOCTL_CDROM_GET_CONTROL request to report the audio playback mode. 



## -syntax

````
typedef struct _CDROM_AUDIO_CONTROL {
  UCHAR  LbaFormat;
  USHORT LogicalBlocksPerSecond;
} CDROM_AUDIO_CONTROL, *PCDROM_AUDIO_CONTROL;
````


## -struct-fields

### -field LbaFormat

Contains the logical block address (LBA) format.  


### -field LogicalBlocksPerSecond

Contains the number of logical blocks per second.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_control.md">IOCTL_CDROM_GET_CONTROL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_AUDIO_CONTROL structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

