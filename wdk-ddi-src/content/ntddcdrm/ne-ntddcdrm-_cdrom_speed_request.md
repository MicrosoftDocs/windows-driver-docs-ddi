---
UID: NE:ntddcdrm._CDROM_SPEED_REQUEST
title: "_CDROM_SPEED_REQUEST"
author: windows-driver-content
description: The CDROM_SPEED_REQUEST enumeration indicates which command that the CD-ROM class driver will use to set the spindle speed of a CD-ROM drive.
old-location: storage\cdrom_speed_request.htm
old-project: storage
ms.assetid: 147d2c1c-c12d-4c39-bec5-579ece083ee7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.cdrom_speed_request, *PCDROM_SPEED_REQUEST, _CDROM_SPEED_REQUEST, ntddcdrm/CDROM_SPEED_REQUEST, structs-CD-ROM_6feeaa4e-8500-4ca8-9d0f-3e29a858eb94.xml, PCDROM_SPEED_REQUEST enumeration pointer [Storage Devices], CdromSetStreaming, ntddcdrm/PCDROM_SPEED_REQUEST, ntddcdrm/CdromSetStreaming, PCDROM_SPEED_REQUEST, CdromSetSpeed, ntddcdrm/CdromSetSpeed, CDROM_SPEED_REQUEST enumeration [Storage Devices], CDROM_SPEED_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	CDROM_SPEED_REQUEST
product: Windows
targetos: Windows
req.typenames: "*PCDROM_SPEED_REQUEST, CDROM_SPEED_REQUEST"
---

# _CDROM_SPEED_REQUEST enumeration


## -description


The CDROM_SPEED_REQUEST enumeration indicates which command that the CD-ROM class driver will use to set the spindle speed of a CD-ROM drive.


## -syntax


````
typedef enum _CDROM_SPEED_REQUEST { 
  CdromSetSpeed      = 0,
  CdromSetStreaming  = 1
} CDROM_SPEED_REQUEST, *PCDROM_SPEED_REQUEST;
````


## -enum-fields




### -field CdromSetSpeed

The CD-ROM class driver will use the SET CD SPEED command to set the spindle speed.


### -field CdromSetStreaming

The CD-ROM class driver will use the SET STREAMING command to set the spindle speed.


## -see-also

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_set_speed.md">CDROM_SET_SPEED</a>

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_set_speed.md">IOCTL_CDROM_SET_SPEED</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_set_streaming.md">CDROM_SET_STREAMING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_SPEED_REQUEST enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

