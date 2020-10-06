---
UID: NS:ntddstor._STORAGE_HW_ENDURANCE_INFO
title: STORAGE_HW_ENDURANCE_INFO
description: A storage port driver uses the **STORAGE_HW_ENDURANCE_INFO** structure to report a device's endurance information.
tech.root: storage
ms.assetid: a2572a43-05b5-45c1-9c4e-c40281affb63
ms.date: 03/13/2019
keywords: ["STORAGE_HW_ENDURANCE_INFO structure"]
ms.keywords: STORAGE_HW_ENDURANCE_INFO, STORAGE_HW_ENDURANCE_INFO, *PSTORAGE_HW_ENDURANCE_INFO,
req.header: ntddstor.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: STORAGE_HW_ENDURANCE_INFO, *PSTORAGE_HW_ENDURANCE_INFO
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _STORAGE_HW_ENDURANCE_INFO
 - ntddstor/_STORAGE_HW_ENDURANCE_INFO
 - PSTORAGE_HW_ENDURANCE_INFO
 - ntddstor/PSTORAGE_HW_ENDURANCE_INFO
 - STORAGE_HW_ENDURANCE_INFO
 - ntddstor/STORAGE_HW_ENDURANCE_INFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - STORAGE_HW_ENDURANCE_INFO
product:
 - Windows
---

# STORAGE_HW_ENDURANCE_INFO structure


## -description

A storage port driver uses the STORAGE_HW_ENDURANCE_INFO structure to report a device's endurance information.

## -struct-fields

### -field ValidFields

Bitmask that indicates which of the remaining members contain valid data. Can be any of the combination of the following bits:

| Bit | Meaning |
|-|-|
| 0 | The *GroupId* member contains valid data. |
| 1 | The *Flags* member contains valid data. |
| 2 | The *LifePercentage* member contains valid data. |
| 3 | The *BytesReadCount* member contains valid data. |
| 4 | Th  *ByteWriteCount* member contains valid data. |

### -field GroupId

ID number that represents a group of resources.

### -field Flags

### -field Flags.Shared

Set TRUE if the endurance information is shared with multiple disks.

### -field Flags.Reserved

Reserved; do not use.

### -field LifePercentage

Percentage of used life. This value is typically between 0-100, where a larger number indicates more life has been used.

### -field BytesReadCount

Total bytes read from the device, specified in billions. For example, a value of 1 would mean 1 billion bytes read.

### -field ByteWriteCount

Total bytes written to the device, specified in billions. For example, a value of 1 would mean 1 billion bytes written.

## -remarks

This structure is a member of [STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR](ns-ntddstor-storage_hw_endurance_data_descriptor.md), which is the structure returned within the output buffer of an [IOCTL_SCSI_MINIPORT](../ntddscsi/ni-ntddscsi-ioctl_scsi_miniport.md) request.

## -see-also

[IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO](../ntddscsi/ni-ntddscsi-ioctl_miniport_signature_endurance_info.md)

[IOCTL_SCSI_MINIPORT](../ntddscsi/ni-ntddscsi-ioctl_scsi_miniport.md)

[STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR](ns-ntddstor-storage_hw_endurance_data_descriptor.md)

