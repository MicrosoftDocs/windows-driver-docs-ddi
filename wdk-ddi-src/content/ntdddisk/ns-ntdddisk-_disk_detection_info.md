---
UID: NS:ntdddisk._DISK_DETECTION_INFO
title: DISK_DETECTION_INFO (ntdddisk.h)
description: The DISK_DETECTION_INFO structure contains the detected drive parameters that are supplied by an x86 PC BIOS on boot.
old-location: storage\disk_detection_info.htm
tech.root: storage
ms.date: 05/20/2022
keywords: ["DISK_DETECTION_INFO structure"]
ms.keywords: "*PDISK_DETECTION_INFO, DISK_DETECTION_INFO, DISK_DETECTION_INFO structure [Storage Devices], PDISK_DETECTION_INFO, PDISK_DETECTION_INFO structure pointer [Storage Devices], _DISK_DETECTION_INFO, ntdddisk/DISK_DETECTION_INFO, ntdddisk/PDISK_DETECTION_INFO, storage.disk_detection_info, structs-disk_04ca1cb1-3995-47d9-9b5a-0e54ea98dbd6.xml"
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
req.typenames: DISK_DETECTION_INFO, *PDISK_DETECTION_INFO
f1_keywords:
 - _DISK_DETECTION_INFO
 - ntdddisk/_DISK_DETECTION_INFO
 - PDISK_DETECTION_INFO
 - ntdddisk/PDISK_DETECTION_INFO
 - DISK_DETECTION_INFO
 - ntdddisk/DISK_DETECTION_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - _DISK_DETECTION_INFO
 - PDISK_DETECTION_INFO
 - DISK_DETECTION_INFO
---

# DISK_DETECTION_INFO structure

## -description

The **DISK_DETECTION_INFO** structure contains the detected drive parameters that are supplied by an x86 PC BIOS on boot.

## -struct-fields

### -field SizeOfDetectInfo

Contains the quantity, in bytes, of retrieved detect information.

### -field DetectionType

A [**DETECTION_TYPE**](ne-ntdddisk-_detection_type.md) value that determines the type of formatting used by the BIOS to record the disk geometry.

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.Int13

A [**DISK_INT13_INFO**](ns-ntdddisk-_disk_int13_info.md) structure when **DetectionType** is **DetectInt13**.

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.ExInt13

A [**DISK_EX_INT13_INFO**](ns-ntdddisk-_disk_ex_int13_info.md) structure when **DetectionType** is **DetectExInt13**.

## -see-also

[**DISK_EX_INT13_INFO**](ns-ntdddisk-_disk_ex_int13_info.md)

[**DISK_GEOMETRY_EX**](ns-ntdddisk-_disk_geometry_ex.md)

[**DISK_INT13_INFO**](ns-ntdddisk-_disk_int13_info.md)
