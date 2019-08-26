---
UID: NS:ntddstor._DEVICE_DSM_OFFLOAD_READ_PARAMETERS
title: _DEVICE_DSM_OFFLOAD_READ_PARAMETERS (ntddstor.h)
description: The DEVICE_DSM_OFFLOAD_READ_PARAMETERS structure specifies the parameters for an offload read action related to the data-set attributes for a device.
old-location: storage\device_dsm_offload_read_parameters.htm
tech.root: storage
ms.assetid: 4C0B2CFD-B981-4304-B3F9-AD534BF5A823
ms.date: 08/23/2019
ms.keywords: "*PDEVICE_DSM_OFFLOAD_READ_PARAMETERS, DEVICE_DSM_OFFLOAD_READ_PARAMETERS, DEVICE_DSM_OFFLOAD_READ_PARAMETERS structure [Storage Devices], PDEVICE_DSM_OFFLOAD_READ_PARAMETERS, PDEVICE_DSM_OFFLOAD_READ_PARAMETERS structure pointer [Storage Devices], _DEVICE_DSM_OFFLOAD_READ_PARAMETERS, ntddstor/DEVICE_DSM_OFFLOAD_READ_PARAMETERS, ntddstor/PDEVICE_DSM_OFFLOAD_READ_PARAMETERS, storage.device_dsm_offload_read_parameters"
ms.topic: struct
f1_keywords:
 - "ntddstor/DEVICE_DSM_OFFLOAD_READ_PARAMETERS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddstor.h
api_name:
- DEVICE_DSM_OFFLOAD_READ_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DEVICE_DSM_OFFLOAD_READ_PARAMETERS, *PDEVICE_DSM_OFFLOAD_READ_PARAMETERS
---

# _DEVICE_DSM_OFFLOAD_READ_PARAMETERS structure

## -description

The DEVICE_DSM_OFFLOAD_READ_PARAMETERS structure specifies the parameters for an offload read action related to the data-set attributes for a device.

## -struct-fields

### -field Flags

Not used. Set to 0.

### -field TimeToLive

The duration, in milliseconds, for which the requested data ranges should remain valid.

### -field Reserved

Reserved.

## -remarks

This structure is used in an offload read action for an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes) request. The **Action** member of the [DEVICE_DSM_INPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes) structure is set to **DeviceDsmAction_OffloadRead**.

The **ParameterBlockOffset** and **ParameterBlockLength** members of [DEVICE_DSM_INPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes) structure are set to the location and length of the DEVICE_DSM_OFFLOAD_READ_PARAMETERS structure in the input buffer of the [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes) request.

The **DataSetRangesOffset** and **DataSetRangesLength** members of DEVICE_DSM_INPUT specify the [DEVICE_DSM_RANGE](ttps://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_data_set_range) structures for the extents of the offload read.

See [DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions) for more details about this action.

## -see-also

[DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions)

[DEVICE_DSM_INPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes)

[DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_dsm_offload_write_parameters)

[DEVICE_DSM_RANGE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_data_set_range)
