---
UID: NE:ntddcdrm._CDROM_SPEED_REQUEST
title: _CDROM_SPEED_REQUEST (ntddcdrm.h)
description: The CDROM_SPEED_REQUEST enumeration indicates which command that the CD-ROM class driver will use to set the spindle speed of a CD-ROM drive.
old-location: storage\cdrom_speed_request.htm
tech.root: storage
ms.assetid: 147d2c1c-c12d-4c39-bec5-579ece083ee7
ms.date: 03/29/2018
ms.keywords: "*PCDROM_SPEED_REQUEST, CDROM_SPEED_REQUEST, CDROM_SPEED_REQUEST enumeration [Storage Devices], CdromSetSpeed, CdromSetStreaming, PCDROM_SPEED_REQUEST, PCDROM_SPEED_REQUEST enumeration pointer [Storage Devices], _CDROM_SPEED_REQUEST, ntddcdrm/CDROM_SPEED_REQUEST, ntddcdrm/CdromSetSpeed, ntddcdrm/CdromSetStreaming, ntddcdrm/PCDROM_SPEED_REQUEST, storage.cdrom_speed_request, structs-CD-ROM_6feeaa4e-8500-4ca8-9d0f-3e29a858eb94.xml"
ms.topic: enum
f1_keywords:
 - "ntddcdrm/CDROM_SPEED_REQUEST"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddcdrm.h
api_name:
- CDROM_SPEED_REQUEST
product:
- Windows
targetos: Windows
req.typenames: CDROM_SPEED_REQUEST, *PCDROM_SPEED_REQUEST
---

# _CDROM_SPEED_REQUEST enumeration


## -description


The CDROM_SPEED_REQUEST enumeration indicates which command that the CD-ROM class driver will use to set the spindle speed of a CD-ROM drive.


## -enum-fields




### -field CdromSetSpeed

The CD-ROM class driver will use the SET CD SPEED command to set the spindle speed.


### -field CdromSetStreaming

The CD-ROM class driver will use the SET STREAMING command to set the spindle speed.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_set_speed">CDROM_SET_SPEED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_set_streaming">CDROM_SET_STREAMING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_set_speed">IOCTL_CDROM_SET_SPEED</a>
 

 

