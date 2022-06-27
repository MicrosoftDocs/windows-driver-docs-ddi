---
UID: NE:ntdddisk._DETECTION_TYPE
title: DETECTION_TYPE (ntdddisk.h)
description: The DETECTION_TYPE enumeration type is used in conjunction with the IOCTL_DISK_GET_DRIVE_GEOMETRY_EX request and the DISK_GEOMETRY_EX structure to determine the type of formatting used by the BIOS to record the disk geometry.
old-location: storage\detection_type.htm
tech.root: storage
ms.date: 05/20/2022
keywords: ["DETECTION_TYPE enumeration"]
ms.keywords: DETECTION_TYPE, DETECTION_TYPE enumeration [Storage Devices], DetectExInt13, DetectInt13, DetectNone, _DETECTION_TYPE, ntdddisk/DETECTION_TYPE, ntdddisk/DetectExInt13, ntdddisk/DetectInt13, ntdddisk/DetectNone, storage.detection_type, structs-disk_2d3d7a57-abcd-43b2-a62d-8b8c45a9fca0.xml
req.header: ntdddisk.h
req.include-header: Ntdddisk.h, Ntddk.h, Ntdddisk.h
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
req.typenames: DETECTION_TYPE
f1_keywords:
 - _DETECTION_TYPE
 - ntdddisk/_DETECTION_TYPE
 - DETECTION_TYPE
 - ntdddisk/DETECTION_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - _DETECTION_TYPE
 - DETECTION_TYPE
---

# DETECTION_TYPE enumeration

## -description

The **DETECTION_TYPE** enumeration type is used in conjunction with the [**IOCTL_DISK_GET_DRIVE_GEOMETRY_EX**](ni-ntdddisk-ioctl_disk_get_drive_geometry_ex.md) request and the [**DISK_GEOMETRY_EX**](ns-ntdddisk-_disk_geometry_ex.md) structure to determine the type of formatting used by the BIOS to record the disk geometry.

## -enum-fields

### -field DetectNone

Indicates that the disk contains neither an INT 13h partition nor an extended INT 13h partition.

### -field DetectInt13

Indicates that the disk has a standard INT 13h partition.

### -field DetectExInt13

Indicates that the disk contains an extended INT 13h partition.

## -remarks

Possible formatting types are the standard INT 13h partition format or the extended INT 13h partition format.

## -see-also

[**DISK_DETECTION_INFO**](ns-ntdddisk-_disk_detection_info.md)
