---
UID: NS:ntddstor._DEVICE_LB_PROVISIONING_DESCRIPTOR
title: DEVICE_LB_PROVISIONING_DESCRIPTOR (ntddstor.h)
description: The DEVICE_LB_PROVISIONING_DESCRIPTOR structure is one of the query result structures returned from an IOCTL_STORAGE_QUERY_PROPERTY request. This structure contains the thin provisioning capabilities for a storage device.
old-location: storage\device_lb_provisioning_descriptor.htm
tech.root: storage
ms.date: 05/20/2022
keywords: ["DEVICE_LB_PROVISIONING_DESCRIPTOR structure"]
ms.keywords: "*PDEVICE_LB_PROVISIONING_DESCRIPTOR, DEVICE_LB_PROVISIONING_DESCRIPTOR, DEVICE_LB_PROVISIONING_DESCRIPTOR structure [Storage Devices], PDEVICE_LB_PROVISIONING_DESCRIPTOR, PDEVICE_LB_PROVISIONING_DESCRIPTOR structure pointer [Storage Devices], _DEVICE_LB_PROVISIONING_DESCRIPTOR, ntddstor/DEVICE_LB_PROVISIONING_DESCRIPTOR, ntddstor/PDEVICE_LB_PROVISIONING_DESCRIPTOR, storage.device_lb_provisioning_descriptor"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.typenames: DEVICE_LB_PROVISIONING_DESCRIPTOR, *PDEVICE_LB_PROVISIONING_DESCRIPTOR
f1_keywords:
 - _DEVICE_LB_PROVISIONING_DESCRIPTOR
 - ntddstor/_DEVICE_LB_PROVISIONING_DESCRIPTOR
 - PDEVICE_LB_PROVISIONING_DESCRIPTOR
 - ntddstor/PDEVICE_LB_PROVISIONING_DESCRIPTOR
 - DEVICE_LB_PROVISIONING_DESCRIPTOR
 - ntddstor/DEVICE_LB_PROVISIONING_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _DEVICE_LB_PROVISIONING_DESCRIPTOR
 - PDEVICE_LB_PROVISIONING_DESCRIPTOR
 - DEVICE_LB_PROVISIONING_DESCRIPTOR
---

# DEVICE_LB_PROVISIONING_DESCRIPTOR structure

## -description

The **DEVICE_LB_PROVISIONING_DESCRIPTOR** structure is one of the query result structures returned from an [**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) request. This structure contains the thin provisioning capabilities for a storage device.

## -struct-fields

### -field Version

The version of this structure.

### -field Size

The size of this structure. This is set to ```sizeof(DEVICE_LB_PROVISIONING_DESCRIPTOR)```.

### -field ThinProvisioningEnabled

The thin provisioning–enabled status.

| Value | Meaning |
| ----- | ------- |
| 0     | Thin provisioning is disabled. |
| 1     | Thin provisioning is enabled.  |

### -field ThinProvisioningReadZeros

Reads to unmapped regions return zeros.

| Value | Meaning |
| ----- | ------- |
| 0     | Data read from unmapped regions is undefined. |
| 1     | Reads return zeros.                           |

### -field AnchorSupported

Support for the anchored LBA mapping state.

| Value | Meaning |
| ----- | ------- |
| 0     | The anchored LBA mapping state is not supported. |
| 1     | The anchored LBA mapping state is supported.     |

### -field UnmapGranularityAlignmentValid

The validity of unmap granularity alignment for the device.

| Value | Meaning |
| ----- | ------- |
| 0     | Unmap granularity alignment is not valid. |
| 1     | Unmap granularity alignment is valid. |

### -field GetFreeSpaceSupported

Indicates support for [**DeviceDsmAction_GetFreeSpace**](/windows-hardware/drivers/storage/device-dsm-action-descriptions).

| Value | Meaning |
| ----- | ------- |
| 0     | **DeviceDsmAction_GetFreeSpace** is not supported. |
| 1     | **DeviceDsmAction_GetFreeSpace** is supported.     |

### -field MapSupported

Indicates support for [**DeviceDsmAction_Map**](/windows-hardware/drivers/storage/device-dsm-action-descriptions).

| Value | Meaning |
| ----- | ------- |
| 0     | **DeviceDsmAction_Map** is not supported. |
| 1     | **DeviceDsmAction_Map** is supported.     |

### -field Reserved1

Reserved; do not use.

### -field OptimalUnmapGranularity

The optimal number of blocks for unmap granularity for the device.

### -field UnmapGranularityAlignment

The current value, in blocks, set for unmap granularity alignment on the device.   The value **UnmapGranularityAlignmentValid** indicates the validity of this member.

### -field MaxUnmapLbaCount

Maximum amount of LBAs that can be unmapped in a single UNMAP command, in units of logical blocks. Valid starting in Windows 10.

### -field MaxUnmapBlockDescriptorCount

Maximum number of descriptors allowed in a single UNMAP command. Valid starting in Windows 10.

## -remarks

This structure is returned in the system buffer from a [**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) request when the **PropertyId** member of [**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md) is set to **StorageDeviceLBProvisioningProperty**.

The **DEVICE_LB_PROVISIONING_DESCRIPTOR** structure is written to the system buffer, **Irp->AssociatedIrp.SystemBuffer**, with a value of **sizeof**(DEVICE_LB_PROVISIONING_DESCRIPTOR) set in **Parameters.DeviceIoControl.OutputBufferLength** for the current IRP stack location.

If **UnmapGranularityAlignmentValid** is 0,  then any code using **UnmapGranularityAlignment** should assume it has a value of 0.

If the underlying storage device is a SCSI device, unmapping capability can be queried. If the **TrimEnabled** member of the [**DEVICE_TRIM_DESCRIPTOR**](ns-ntddstor-_device_trim_descriptor.md) structure is TRUE, UNMAP is supported. The **DEVICE_TRIM_DESCRIPTOR** structure is returned in the system buffer from a [**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) request when the **PropertyId** member of [**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md) is set to **StorageDeviceTrimProperty**.

## -see-also

[**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md)

[**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md)
