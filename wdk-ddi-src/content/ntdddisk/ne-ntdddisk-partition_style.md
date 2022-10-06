---
UID: NE:ntdddisk._PARTITION_STYLE
tech.root: storage
title: PARTITION_STYLE
ms.date: 09/30/2022
targetos: Windows
description: Learn more about the PARTITION_STYLE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntdddisk.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - _PARTITION_STYLE
 - PARTITION_STYLE
f1_keywords:
 - _PARTITION_STYLE
 - ntdddisk/_PARTITION_STYLE
 - PARTITION_STYLE
 - ntdddisk/PARTITION_STYLE
dev_langs:
 - c++
helpviewer_keywords:
 - _PARTITION_STYLE
---

## -description

The PARTITION\_STYLE enumeration type indicates the type of partition table for a disk.

## -enum-fields

### -field PARTITION_STYLE_MBR

Specifies the traditional, AT-style Master Boot Record, type of partition table.

### -field PARTITION_STYLE_GPT

Specifies the GUID Partition Table type of partition table.

### -field PARTITION_STYLE_RAW

The partition is not formatted in either of the recognized formats — MBR or GPT.

## -remarks

The GUID Partition Table format conforms to the Extensible Firmware Interface (EFI) standard developed by Intel. For further information, see Intel's *Extensible Firmware Interface* specification.

## -see-also

[**CREATE\_DISK**](ns-ntdddisk-_create_disk.md)

[**DISK\_PARTITION\_INFO**](ns-ntdddisk-_disk_partition_info.md)

[**PARTITION\_INFORMATION\_EX**](ns-ntdddisk-_partition_information_ex.md)
