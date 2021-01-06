---
UID: NS:ntddstor._STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR
title: STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR
description: A storage port driver uses the **STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR** structure to report a device's endurance information.
tech.root: storage
ms.date: 03/18/2019
keywords: ["STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR structure"]
ms.keywords: STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR, STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR, *PSTORAGE_HW_ENDURANCE_DATA_DESCRIPTOR, IOCTL_MINIPORT_ENDURANCE_INFO, IOCTL_SCSI_MINIPORT, STORAGE_HW_ENDURANCE_INFO, STORAGE_ENDURANCE_DATA_DESCRIPTOR
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
req.typenames: STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR, *PSTORAGE_HW_ENDURANCE_DATA_DESCRIPTOR
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR
 - ntddstor/_STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR
 - PSTORAGE_HW_ENDURANCE_DATA_DESCRIPTOR
 - ntddstor/PSTORAGE_HW_ENDURANCE_DATA_DESCRIPTOR
 - STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR
 - ntddstor/STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR
product:
 - Windows
---

# STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR structure


## -description

A storage port driver uses the STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR structure to report a device's endurance information.

## -struct-fields

### -field Version

Version of this structure. Set this to be **sizeof**(STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR).

### -field Size

Size, in bytes, of the buffer containing the endurance information. Set this to be **sizeof**(STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR).

### -field EnduranceInfo

A [STORAGE_HW_ENDURANCE_INFO](ns-ntddstor-storage_hw_endurance_info.md) structure in which to store the device's endurance information.

## -remarks

A storage port driver uses this structure when communicating with its miniport for an [IOCTL_SCSI_MINIPORT](../ntddscsi/ni-ntddscsi-ioctl_scsi_miniport.md) request that has an [SRB_IO_CONTROL](../ntddscsi/ns-ntddscsi-_srb_io_control.md) structure with a **Signature** of [IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO](../ntddscsi/ni-ntddscsi-ioctl_miniport_signature_endurance_info.md), and a **ControlCode** of[IOCTL_STORAGE_QUERY_PROPERTY](./ni-ntddstor-ioctl_storage_query_property.md) with a **PropertyId** of StorageDeviceEnduranceProperty and a **QueryType** of PropertyStandardQuery.

The miniport uses [STORAGE_ENDURANCE_DATA_DESCRIPTOR](../ntddscsi/ns-ntddscsi-storage_endurance_data_descriptor.md), which is defined in *ntddscsi.h*. STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR and STORAGE_ENDURANCE_DATA_DESCRIPTOR are identical in size, so the storage port driver and miniport should cast the structure they receive accordingly when communicating with each other.

## -see-also

[IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO](../ntddscsi/ni-ntddscsi-ioctl_miniport_signature_endurance_info.md)

[IOCTL_SCSI_MINIPORT](../ntddscsi/ni-ntddscsi-ioctl_scsi_miniport.md)

[IOCTL_STORAGE_QUERY_PROPERTY](./ni-ntddstor-ioctl_storage_query_property.md)

[SRB_IO_CONTROL](../ntddscsi/ns-ntddscsi-_srb_io_control.md)

[STORAGE_ENDURANCE_DATA_DESCRIPTOR](../ntddscsi/ns-ntddscsi-storage_endurance_data_descriptor.md)

[STORAGE_HW_ENDURANCE_INFO](ns-ntddstor-storage_hw_endurance_info.md)
