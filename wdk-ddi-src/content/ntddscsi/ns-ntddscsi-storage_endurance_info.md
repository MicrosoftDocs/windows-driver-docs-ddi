---
UID: NS:ntddscsi._STORAGE_ENDURANCE_INFO
title: STORAGE_ENDURANCE_INFO
description: A miniport uses the **STORAGE_ENDURANCE_INFO** structure to report a device's endurance information.
tech.root: storage
ms.date: 03/15/2019
keywords: ["STORAGE_ENDURANCE_INFO structure"]
ms.keywords: STORAGE_ENDURANCE_INFO, STORAGE_ENDURANCE_INFO, *PSTORAGE_ENDURANCE_INFO, STORAGE_ENDURANCE_DATA_DESCRIPTOR
req.header: ntddscsi.h
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
req.typenames: STORAGE_ENDURANCE_INFO, *PSTORAGE_ENDURANCE_INFO
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _STORAGE_ENDURANCE_INFO
 - ntddscsi/_STORAGE_ENDURANCE_INFO
 - PSTORAGE_ENDURANCE_INFO
 - ntddscsi/PSTORAGE_ENDURANCE_INFO
 - STORAGE_ENDURANCE_INFO
 - ntddscsi/STORAGE_ENDURANCE_INFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddscsi.h
api_name:
 - _STORAGE_ENDURANCE_INFO
 - PSTORAGE_ENDURANCE_INFO
 - STORAGE_ENDURANCE_INFO
---

# STORAGE_ENDURANCE_INFO structure


## -description

A miniport uses the **STORAGE_ENDURANCE_INFO** structure to report a device's endurance information.

## -struct-fields

### -field ValidFields

Bitmask that indicates which of the remaining members contain valid data. Can be any of the combination of the following bits:

| Bit | Meaning |
|-|-|
| 0 | The *GroupId* member contains valid data. |
| 1 | The *Flags* member contains valid data. |
| 2 | The *LifePercentage* member contains valid data. |
| 3 | The *BytesReadCount* member contains valid data. |
| 4 | The *ByteWriteCount* member contains valid data. |

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

This structure is a member of [STORAGE_ENDURANCE_DATA_DESCRIPTOR](ns-ntddscsi-storage_endurance_data_descriptor.md), which is the structure returned within the output buffer of an [IOCTL_SCSI_MINIPORT](ni-ntddscsi-ioctl_scsi_miniport.md) request with a **Signature** of [IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO](ni-ntddscsi-ioctl_miniport_signature_endurance_info.md).

## -see-also

[IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO](ni-ntddscsi-ioctl_miniport_signature_endurance_info.md)

[IOCTL_SCSI_MINIPORT](ni-ntddscsi-ioctl_scsi_miniport.md)

[STORAGE_ENDURANCE_DATA_DESCRIPTOR](ns-ntddscsi-storage_endurance_data_descriptor.md)

[STORAGE_HW_ENDURANCE_INFO]/ntddstor/ns-ntddstor-storage_hw_endurance_info.md)

