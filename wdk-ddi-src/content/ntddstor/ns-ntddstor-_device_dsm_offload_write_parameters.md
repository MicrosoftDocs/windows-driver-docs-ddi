---
UID: NS:ntddstor._DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS
title: _DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS (ntddstor.h)
description: The DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS structure specifies the parameters for an offload write action related to the data-set attributes for a device.
old-location: storage\device_dsm_offload_write_parameters.htm
tech.root: storage
ms.date: 08/23/2019
keywords: ["DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS structure"]
ms.keywords: "*PDEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS structure [Storage Devices], PDEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, PDEVICE_DSM_OFFLOAD_WRITE_PARAMETERS structure pointer [Storage Devices], _DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, ntddstor/DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, ntddstor/PDEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, storage.device_dsm_offload_write_parameters"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
req.typenames: DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, *PDEVICE_DSM_OFFLOAD_WRITE_PARAMETERS
f1_keywords:
 - _DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS
 - ntddstor/_DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS
 - PDEVICE_DSM_OFFLOAD_WRITE_PARAMETERS
 - ntddstor/PDEVICE_DSM_OFFLOAD_WRITE_PARAMETERS
 - DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS
 - ntddstor/DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS
---

# _DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS structure


## -description

The DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS structure specifies the parameters for an offload write action related to the data-set attributes for a device.

## -struct-fields

### -field Flags

Not used.

### -field Reserved

Reserved.

### -field TokenOffset

The offset, in bytes, within the data block specified by **Token** to begin writing from.

### -field Token

The unique identifier of the data block to write from.

## -remarks

This structure is used in an offload write action for an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md) request.  The **Action** member of the [DEVICE_DSM_INPUT](./ns-ntddstor-_device_manage_data_set_attributes.md) structure is set to **DeviceDsmAction_OffloadWrite**.

The **ParameterBlockOffset** and **ParameterBlockLength** members  of [DEVICE_DSM_INPUT](./ns-ntddstor-_device_manage_data_set_attributes.md) are set to the location and length of the DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS structure in the system buffer of the [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md) request.

The **DataSetRangesOffset** and **DataSetRangesLength** members of DEVICE_DSM_INPUT specify the [DEVICE_DSM_RANGE](./ns-ntddstor-_device_data_set_range.md) structures for the extents of the offload write.

See [DEVICE_DSM_ACTION Descriptions](/windows-hardware/drivers/storage/device-dsm-action-descriptions) for more details about this action.

## -see-also

[DEVICE_DSM_ACTION Descriptions](/windows-hardware/drivers/storage/device-dsm-action-descriptions)

[DEVICE_DSM_INPUT](./ns-ntddstor-_device_manage_data_set_attributes.md)

[DEVICE_DSM_OFFLOAD_READ_PARAMETERS](./ns-ntddstor-_device_dsm_offload_read_parameters.md)

[DEVICE_DSM_RANGE](./ns-ntddstor-_device_data_set_range.md)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md)
