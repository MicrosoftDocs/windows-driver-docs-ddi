---
UID: NS:ntddcdrm._CDROM_SEEK_AUDIO_MSF
title: "_CDROM_SEEK_AUDIO_MSF"
author: windows-driver-content
description: The CDROM_SEEK_AUDIO_MSF structure contains the minute, second, and frame that the device must seek to upon receipt of a device control IRP with a control code of IOCTL_CDROM_SEEK_AUDIO_MSF.
old-location: storage\cdrom_seek_audio_msf.htm
old-project: storage
ms.assetid: 8fd4e642-5ed4-409e-bcc2-94d309a1e04c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: CDROM_SEEK_AUDIO_MSF structure [Storage Devices], ntddcdrm/CDROM_SEEK_AUDIO_MSF, PCDROM_SEEK_AUDIO_MSF structure pointer [Storage Devices], structs-CD-ROM_1e8a9382-37c6-4473-831e-3547774a5b9d.xml, ntddcdrm/PCDROM_SEEK_AUDIO_MSF, _CDROM_SEEK_AUDIO_MSF, PCDROM_SEEK_AUDIO_MSF, *PCDROM_SEEK_AUDIO_MSF, storage.cdrom_seek_audio_msf, CDROM_SEEK_AUDIO_MSF
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
-	CDROM_SEEK_AUDIO_MSF
product: Windows
targetos: Windows
req.typenames: "*PCDROM_SEEK_AUDIO_MSF, CDROM_SEEK_AUDIO_MSF"
---

# _CDROM_SEEK_AUDIO_MSF structure


## -description


The CDROM_SEEK_AUDIO_MSF structure contains the minute, second, and frame that the device must seek to upon receipt of a device control IRP with a control code of <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_seek_audio_msf.md">IOCTL_CDROM_SEEK_AUDIO_MSF</a>. 


## -syntax


````
typedef struct _CDROM_SEEK_AUDIO_MSF {
  UCHAR M;
  UCHAR S;
  UCHAR F;
} CDROM_SEEK_AUDIO_MSF, *PCDROM_SEEK_AUDIO_MSF;
````


## -struct-fields




### -field M

Contains an integer between 0 and 74 that indicates the minute to seek to.


### -field S

Contains an integer between 0 and 59 that indicates the second to seek to.


### -field F

Contains an integer between 0 and 74 that indicates the frame to seek to.


## -see-also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_seek_audio_msf.md">IOCTL_CDROM_SEEK_AUDIO_MSF</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_SEEK_AUDIO_MSF structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

