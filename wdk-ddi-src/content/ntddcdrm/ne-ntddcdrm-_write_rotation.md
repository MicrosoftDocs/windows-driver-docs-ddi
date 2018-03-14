---
UID: NE:ntddcdrm._WRITE_ROTATION
title: "_WRITE_ROTATION"
author: windows-driver-content
description: The WRITE_ROTATION enumeration specifies whether a CD-ROM drive uses constant linear velocity (CLV) rotation or constant angular velocity (CAV) rotation when it writes to a CD.
old-location: storage\write_rotation.htm
old-project: storage
ms.assetid: e3569e38-cb56-4e33-baba-c479fc4368da
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWRITE_ROTATION, CdromCAVRotation, CdromDefaultRotation, PWRITE_ROTATION, PWRITE_ROTATION enumeration pointer [Storage Devices], WRITE_ROTATION, WRITE_ROTATION enumeration [Storage Devices], _WRITE_ROTATION, ntddcdrm/CdromCAVRotation, ntddcdrm/CdromDefaultRotation, ntddcdrm/PWRITE_ROTATION, ntddcdrm/WRITE_ROTATION, storage.write_rotation, structs-CD-ROM_1fcb9104-97bd-48bf-8f08-66b292cd9045.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddcdrm.h
api_name:
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

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_set_speed.md">IOCTL_CDROM_SET_SPEED</a>



<a href="..\ntddcdrm\ne-ntddcdrm-_cdrom_speed_request.md">CDROM_SPEED_REQUEST</a>



 

 


