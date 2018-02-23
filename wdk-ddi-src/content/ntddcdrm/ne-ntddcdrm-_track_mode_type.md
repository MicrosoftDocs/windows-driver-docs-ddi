---
UID: NE:ntddcdrm._TRACK_MODE_TYPE
title: "_TRACK_MODE_TYPE"
author: windows-driver-content
description: The TRACK_MODE_TYPE enumeration type is used in conjunction with the IOCTL_CDROM_RAW_READ request and the RAW_READ_INFO structure to read data from a CD-ROM in raw mode.
old-location: storage\track_mode_type.htm
old-project: storage
ms.assetid: ea7d7b5a-625f-41f7-b3fd-96a6bf338db9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddcdrm/CDDA, PTRACK_MODE_TYPE enumeration pointer [Storage Devices], ntddcdrm/XAForm2, CDDA, ntddcdrm/RawWithSubCode, ntddcdrm/RawWithC2AndSubCode, ntddcdrm/TRACK_MODE_TYPE, TRACK_MODE_TYPE, _TRACK_MODE_TYPE, ntddcdrm/YellowMode2, RawWithC2AndSubCode, YellowMode2, structs-CD-ROM_41364f33-e1bf-48ac-abb6-4cacf5283f9f.xml, RawWithSubCode, RawWithC2, PTRACK_MODE_TYPE, TRACK_MODE_TYPE enumeration [Storage Devices], *PTRACK_MODE_TYPE, storage.track_mode_type, ntddcdrm/PTRACK_MODE_TYPE, XAForm2, ntddcdrm/RawWithC2
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
-	TRACK_MODE_TYPE
product: Windows
targetos: Windows
req.typenames: TRACK_MODE_TYPE, *PTRACK_MODE_TYPE
---

# _TRACK_MODE_TYPE enumeration


## -description


The TRACK_MODE_TYPE enumeration type is used in conjunction with the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_raw_read.md">IOCTL_CDROM_RAW_READ</a> request and the <a href="..\ntddcdrm\ns-ntddcdrm-__raw_read_info.md">RAW_READ_INFO</a> structure to read data from a CD-ROM in raw mode.  


## -syntax


````
typedef enum _TRACK_MODE_TYPE { 
  YellowMode2          = 0,
  XAForm2              = 1,
  CDDA                 = 2,
  RawWithC2AndSubCode  = 3,
  RawWithC2            = 4,
  RawWithSubCode       = 5
} TRACK_MODE_TYPE, *PTRACK_MODE_TYPE;
````


## -enum-fields




### -field YellowMode2

Indicates that CD-ROM mode should be used. This mode is used with read-only 120 mm Optical Data Discs (CD-ROM). For more information, see the ISO/IEC 10149 specification.


### -field XAForm2

Indicates that compact disc read-only memory extended architecture mode should be used. For more information see the specification for CD-ROM XA published by NV Philips and Sony Corporation.


### -field CDDA

Indicates that digital audio information mode should be used. For more information, see the IEC 908:1987 specification.


### -field RawWithC2AndSubCode

CD_RAW_SECTOR_WITH_C2_AND_SUBCODE_SIZE per sector


### -field RawWithC2

CD_RAW_SECTOR_WITH_C2_SIZE per sector


### -field RawWithSubCode

CD_RAW_SECTOR_WITH_SUBCODE_SIZE per sector


## -see-also

<a href="..\ntddcdrm\ns-ntddcdrm-__raw_read_info.md">RAW_READ_INFO</a>



<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_raw_read.md">IOCTL_CDROM_RAW_READ</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TRACK_MODE_TYPE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

