---
UID: NE:ntddcdrm._WRITE_ROTATION
title: "_WRITE_ROTATION" (ntddcdrm.h)
description: The WRITE_ROTATION enumeration specifies whether a CD-ROM drive uses constant linear velocity (CLV) rotation or constant angular velocity (CAV) rotation when it writes to a CD.
old-location: storage\write_rotation.htm
tech.root: storage
ms.assetid: e3569e38-cb56-4e33-baba-c479fc4368da
ms.date: 03/29/2018
ms.keywords: "*PWRITE_ROTATION, CdromCAVRotation, CdromDefaultRotation, PWRITE_ROTATION, PWRITE_ROTATION enumeration pointer [Storage Devices], WRITE_ROTATION, WRITE_ROTATION enumeration [Storage Devices], _WRITE_ROTATION, ntddcdrm/CdromCAVRotation, ntddcdrm/CdromDefaultRotation, ntddcdrm/PWRITE_ROTATION, ntddcdrm/WRITE_ROTATION, storage.write_rotation, structs-CD-ROM_1fcb9104-97bd-48bf-8f08-66b292cd9045.xml"
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
product:
- Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# _WRITE_ROTATION enumeration


## -description


The WRITE_ROTATION enumeration specifies whether a CD-ROM drive uses constant linear velocity (CLV) rotation or constant angular velocity (CAV) rotation when it writes to a CD.


## -enum-fields




### -field CdromDefaultRotation

The CD-ROM drive uses the (default) constant linear velocity (CLV) method when it writes to a CD.


### -field CdromCAVRotation

The CD-ROM drive uses the (default) constant angular velocity (CAV) method when it writes to a CD.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551370">CDROM_SPEED_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559381">IOCTL_CDROM_SET_SPEED</a>
 

 

