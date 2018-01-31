---
UID: NS:ntddcdrm._CDROM_SET_SPEED
title: "_CDROM_SET_SPEED"
author: windows-driver-content
description: The CDROM_SET_SPEED structure is used with the IOCTL_CDROM_SET_SPEED request to set the spindle speed of a CD-ROM drive during data transfers in which no data loss is permitted.
old-location: storage\cdrom_set_speed.htm
old-project: storage
ms.assetid: 42cffab4-d8a7-4dff-9f53-19aa2769a85c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: structs-CD-ROM_e6e6b227-c3d9-4976-b1a5-a2100c49d266.xml, ntddcdrm/PCDROM_SET_SPEED, PCDROM_SET_SPEED, _CDROM_SET_SPEED, CDROM_SET_SPEED, PCDROM_SET_SPEED structure pointer [Storage Devices], *PCDROM_SET_SPEED, CDROM_SET_SPEED structure [Storage Devices], storage.cdrom_set_speed, ntddcdrm/CDROM_SET_SPEED
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
-	CDROM_SET_SPEED
product: Windows
targetos: Windows
req.typenames: CDROM_SET_SPEED, *PCDROM_SET_SPEED
---

# _CDROM_SET_SPEED structure


## -description


The CDROM_SET_SPEED structure is used with the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_set_speed.md">IOCTL_CDROM_SET_SPEED</a> request to set the spindle speed of a CD-ROM drive during data transfers in which no data loss is permitted.


## -syntax


````
typedef struct _CDROM_SET_SPEED {
  CDROM_SPEED_REQUEST RequestType;
  USHORT              ReadSpeed;
  USHORT              WriteSpeed;
  WRITE_ROTATION      RotationControl;
} CDROM_SET_SPEED, *PCDROM_SET_SPEED;
````


## -struct-fields




#### - RequestType

A <a href="..\ntddcdrm\ne-ntddcdrm-_cdrom_speed_request.md">CDROM_SPEED_REQUEST</a>-typed value that indicates the type of set speed operation for <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_set_speed.md">IOCTL_CDROM_SET_SPEED</a> to perform.


#### - ReadSpeed

The read speed, in kilobytes per second.


#### - WriteSpeed

The write speed, in kilobytes per second.


#### - RotationControl

A <a href="..\ntddcdrm\ne-ntddcdrm-_write_rotation.md">WRITE_ROTATION</a>-typed value that indicates whether the drive uses constant angular velocity (CAV) or constant linear velocity (CLV) rotation when it writes to a CD.


## -see-also

<a href="..\ntddcdrm\ne-ntddcdrm-_write_rotation.md">WRITE_ROTATION</a>

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_set_speed.md">IOCTL_CDROM_SET_SPEED</a>

<a href="..\ntddcdrm\ne-ntddcdrm-_cdrom_speed_request.md">CDROM_SPEED_REQUEST</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_set_streaming.md">CDROM_SET_STREAMING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_SET_SPEED structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

