---
UID: NS:ntddstor._DEVICE_DATA_SET_REPAIR_PARAMETERS
title: _DEVICE_DATA_SET_REPAIR_PARAMETERS (ntddstor.h)
description: The DEVICE_DATA_SET_REPAIR_PARAMETERS structure specifies the parameters of a storage spaces repair operation specified for a data set management action.
old-location: storage\device_data_set_repair_parameters.htm
tech.root: storage
ms.assetid: BBA834D0-4D21-42EF-98B0-9AF3FF28E6E2
ms.date: 08/23/2019
keywords: ["DEVICE_DATA_SET_REPAIR_PARAMETERS structure"]
ms.keywords: "*PDEVICE_DATA_SET_REPAIR_PARAMETERS, DEVICE_DATA_SET_REPAIR_PARAMETERS, DEVICE_DATA_SET_REPAIR_PARAMETERS structure [Storage Devices], PDEVICE_DATA_SET_REPAIR_PARAMETERS, PDEVICE_DATA_SET_REPAIR_PARAMETERS structure pointer [Storage Devices], _DEVICE_DATA_SET_REPAIR_PARAMETERS, ntddstor/DEVICE_DATA_SET_REPAIR_PARAMETERS, ntddstor/PDEVICE_DATA_SET_REPAIR_PARAMETERS, storage.device_data_set_repair_parameters"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.typenames: DEVICE_DATA_SET_REPAIR_PARAMETERS, *PDEVICE_DATA_SET_REPAIR_PARAMETERS
f1_keywords:
 - _DEVICE_DATA_SET_REPAIR_PARAMETERS
 - ntddstor/_DEVICE_DATA_SET_REPAIR_PARAMETERS
 - PDEVICE_DATA_SET_REPAIR_PARAMETERS
 - ntddstor/PDEVICE_DATA_SET_REPAIR_PARAMETERS
 - DEVICE_DATA_SET_REPAIR_PARAMETERS
 - ntddstor/DEVICE_DATA_SET_REPAIR_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - DEVICE_DATA_SET_REPAIR_PARAMETERS
---

# _DEVICE_DATA_SET_REPAIR_PARAMETERS structure


## -description

The DEVICE_DATA_SET_REPAIR_PARAMETERS structure specifies the parameters of a storage spaces repair operation specified for a data set management action.

This parameter structure is used in a repair action for an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes) request.  The **Action** member of the [DEVICE_DSM_INPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_manage_data_set_attributes) structure is set to **DeviceDsmAction_Repair**, and **ParameterBlockOffset** indicates the location of DEVICE_DATA_SET_REPAIR_PARAMETERS.

## -struct-fields

### -field NumberOfRepairCopies

The total  number of copies to repair.

### -field SourceCopy

The source copy number.

### -field RepairCopies

An array of copy numbers for the copies to repair.

## -remarks

The **ParameterBlockOffset** and **ParameterBlockLength** members of [DEVICE_DSM_INPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_manage_data_set_attributes) are set to the location and length of the DEVICE_DATA_SET_REPAIR_PARAMETERS structure in the system buffer of the [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes) request.

The **DataSetRangesOffset** and **DataSetRangesLength** members of DEVICE_DSM_INPUT specify the [DEVICE_DSM_RANGE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_data_set_range) structures containing the extents of the repair copies.

## -see-also

[DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions)

[DEVICE_DSM_INPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_manage_data_set_attributes)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes)

