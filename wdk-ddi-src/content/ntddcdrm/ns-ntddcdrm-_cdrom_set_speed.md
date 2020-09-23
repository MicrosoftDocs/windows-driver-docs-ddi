---
UID: NS:ntddcdrm._CDROM_SET_SPEED
title: _CDROM_SET_SPEED (ntddcdrm.h)
description: The CDROM_SET_SPEED structure is used with the IOCTL_CDROM_SET_SPEED request to set the spindle speed of a CD-ROM drive during data transfers in which no data loss is permitted.
old-location: storage\cdrom_set_speed.htm
tech.root: storage
ms.assetid: 42cffab4-d8a7-4dff-9f53-19aa2769a85c
ms.date: 03/29/2018
keywords: ["CDROM_SET_SPEED structure"]
ms.keywords: "*PCDROM_SET_SPEED, CDROM_SET_SPEED, CDROM_SET_SPEED structure [Storage Devices], PCDROM_SET_SPEED, PCDROM_SET_SPEED structure pointer [Storage Devices], _CDROM_SET_SPEED, ntddcdrm/CDROM_SET_SPEED, ntddcdrm/PCDROM_SET_SPEED, storage.cdrom_set_speed, structs-CD-ROM_e6e6b227-c3d9-4976-b1a5-a2100c49d266.xml"
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
targetos: Windows
req.typenames: CDROM_SET_SPEED, *PCDROM_SET_SPEED
f1_keywords:
 - _CDROM_SET_SPEED
 - ntddcdrm/_CDROM_SET_SPEED
 - PCDROM_SET_SPEED
 - ntddcdrm/PCDROM_SET_SPEED
 - CDROM_SET_SPEED
 - ntddcdrm/CDROM_SET_SPEED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdrm.h
api_name:
 - CDROM_SET_SPEED
---

# _CDROM_SET_SPEED structure


## -description

The CDROM_SET_SPEED structure is used with the <a href="/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_set_speed">IOCTL_CDROM_SET_SPEED</a> request to set the spindle speed of a CD-ROM drive during data transfers in which no data loss is permitted.

## -struct-fields

### -field RequestType

A <a href="/windows-hardware/drivers/ddi/ntddcdrm/ne-ntddcdrm-_cdrom_speed_request">CDROM_SPEED_REQUEST</a>-typed value that indicates the type of set speed operation for <a href="/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_set_speed">IOCTL_CDROM_SET_SPEED</a> to perform.

### -field ReadSpeed

The read speed, in kilobytes per second.

### -field WriteSpeed

The write speed, in kilobytes per second.

### -field RotationControl

A <a href="/windows-hardware/drivers/ddi/ntddcdrm/ne-ntddcdrm-_write_rotation">WRITE_ROTATION</a>-typed value that indicates whether the drive uses constant angular velocity (CAV) or constant linear velocity (CLV) rotation when it writes to a CD.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_set_streaming">CDROM_SET_STREAMING</a>



<a href="/windows-hardware/drivers/ddi/ntddcdrm/ne-ntddcdrm-_cdrom_speed_request">CDROM_SPEED_REQUEST</a>



<a href="/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_set_speed">IOCTL_CDROM_SET_SPEED</a>



<a href="/windows-hardware/drivers/ddi/ntddcdrm/ne-ntddcdrm-_write_rotation">WRITE_ROTATION</a>