---
UID: NS:ntddscsi._STORAGE_ENDURANCE_DATA_DESCRIPTOR
title: STORAGE_ENDURANCE_DATA_DESCRIPTOR
author: windows-driver-content
description: A miniport uses STORAGE_ENDURANCE_DATA_DESCRIPTOR to report a device's endurance information to the storage port driver.
tech.root: storage
ms.assetid: b28ee9f0-f089-4b13-a9b7-5c2521dc8105
ms.author: windowsdriverdev
ms.date: 03/18/2019
keywords: ["STORAGE_ENDURANCE_DATA_DESCRIPTOR structure"]
f1_keywords:
 - "ntddscsi/STORAGE_ENDURANCE_DATA_DESCRIPTOR"
ms.keywords: STORAGE_ENDURANCE_DATA_DESCRIPTOR, STORAGE_ENDURANCE_DATA_DESCRIPTOR, *PSTORAGE_ENDURANCE_DATA_DESCRIPTOR, IOCTL_MINIPORT_ENDURANCE_INFO, IOCTL_SCSI_MINIPORT, STORAGE_ENDURANCE_INFO, STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR,
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
req.typenames: STORAGE_ENDURANCE_DATA_DESCRIPTOR, *PSTORAGE_ENDURANCE_DATA_DESCRIPTOR
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddscsi.h
api_name: 
 - STORAGE_ENDURANCE_DATA_DESCRIPTOR
product:
 - Windows
targetos: Windows
ms.custom: 19H1
---

# STORAGE_ENDURANCE_DATA_DESCRIPTOR structure

## -description

A miniport uses **STORAGE_ENDURANCE_DATA_DESCRIPTOR** to report a device's endurance information to the storage port driver.

## -struct-fields

### -field Version

Version of this structure. Set this to be **sizeof**(STORAGE_ENDURANCE_DATA_DESCRIPTOR).

### -field Size

Size, in bytes, of the buffer containing the endurance information. Set this to be **sizeof**(STORAGE_ENDURANCE_DATA_DESCRIPTOR).

### -field EnduranceInfo

A [STORAGE_ENDURANCE_INFO](ns-ntddscsi-storage_endurance_info.md) structure in which to store the device's endurance information.

## -remarks

The miniport returns this structure when handling an [IOCTL_SCSI_MINIPORT](ni-ntddscsi-ioctl_scsi_miniport.md) request that has an [SRB_IO_CONTROL](ns-ntddscsi-_srb_io_control.md) structure with a **Signature** of [IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO](ni-ntddscsi-ioctl_miniport_signature_endurance_info.md), and a **ControlCode** of [IOCTL_STORAGE_QUERY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property) with a **PropertyId** of StorageDeviceEnduranceProperty and a **QueryType** of PropertyStandardQuery.

The storage port driver uses [STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR](../ntddstor/ns-ntddstor-storage_hw_endurance_data_descriptor.md), which is defined in *ntddstor.h*. **STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR** and **STORAGE_ENDURANCE_DATA_DESCRIPTOR** are identical in size, so the storage port driver and miniport should cast the structure they receive accordingly when communicating with each other.

## -see-also

[IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO](ni-ntddscsi-ioctl_miniport_signature_endurance_info.md)

[IOCTL_SCSI_MINIPORT](ni-ntddscsi-ioctl_scsi_miniport.md)

[IOCTL_STORAGE_QUERY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property)

[SRB_IO_CONTROL](ns-ntddscsi-_srb_io_control.md)

[STORAGE_ENDURANCE_INFO](ns-ntddscsi-storage_endurance_info.md)

[STORAGE_HW_ENDURANCE_DATA_DESCRIPTOR](../ntddstor/ns-ntddstor-storage_hw_endurance_data_descriptor.md)
