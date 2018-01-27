---
UID: NE:ntddcdrm._WRITE_ROTATION
title: _WRITE_ROTATION
author: windows-driver-content
description: The WRITE_ROTATION enumeration specifies whether a CD-ROM drive uses constant linear velocity (CLV) rotation or constant angular velocity (CAV) rotation when it writes to a CD.
old-location: storage\write_rotation.htm
old-project: storage
ms.assetid: e3569e38-cb56-4e33-baba-c479fc4368da
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.write_rotation, CdromCAVRotation, PWRITE_ROTATION, ntddcdrm/CdromDefaultRotation, structs-CD-ROM_1fcb9104-97bd-48bf-8f08-66b292cd9045.xml, _WRITE_ROTATION, WRITE_ROTATION enumeration [Storage Devices], ntddcdrm/WRITE_ROTATION, ntddcdrm/CdromCAVRotation, PWRITE_ROTATION enumeration pointer [Storage Devices], *PWRITE_ROTATION, ntddcdrm/PWRITE_ROTATION, WRITE_ROTATION, CdromDefaultRotation
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
-	WRITE_ROTATION
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# _WRITE_ROTATION enumeration


## -description


The WRITE_ROTATION enumeration specifies whether a CD-ROM drive uses constant linear velocity (CLV) rotation or constant angular velocity (CAV) rotation when it writes to a CD.


## -syntax


````
typedef enum _WRITE_ROTATION { 
  CdromDefaultRotation  = 0,
  CdromCAVRotation      = 1
} WRITE_ROTATION, *PWRITE_ROTATION;
````


## -enum-fields




### -field CdromDefaultRotation

The CD-ROM drive uses the (default) constant linear velocity (CLV) method when it writes to a CD.


### -field CdromCAVRotation

The CD-ROM drive uses the (default) constant angular velocity (CAV) method when it writes to a CD.


## -see-also

<a href="..\ntddcdrm\ne-ntddcdrm-_cdrom_speed_request.md">CDROM_SPEED_REQUEST</a>

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_set_speed.md">IOCTL_CDROM_SET_SPEED</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20WRITE_ROTATION enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

