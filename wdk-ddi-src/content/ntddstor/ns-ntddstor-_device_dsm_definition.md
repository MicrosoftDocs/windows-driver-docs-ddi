---
UID: NS:ntddstor._DEVICE_DSM_DEFINITION
title: _DEVICE_DSM_DEFINITION (ntddstor.h)
description: The DEVICE_DSM_DEFINITION structure contains the properties for a data set management (DSM) action.
tech.root: storage
ms.date: 08/23/2019
keywords: ["DEVICE_DSM_DEFINITION structure"]
ms.keywords: _DEVICE_DSM_DEFINITION, DEVICE_DSM_DEFINITION, *PDEVICE_DSM_DEFINITION,
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
req.typenames: DEVICE_DSM_DEFINITION, *PDEVICE_DSM_DEFINITION
targetos: Windows
f1_keywords:
 - _DEVICE_DSM_DEFINITION
 - ntddstor/_DEVICE_DSM_DEFINITION
 - PDEVICE_DSM_DEFINITION
 - ntddstor/PDEVICE_DSM_DEFINITION
 - DEVICE_DSM_DEFINITION
 - ntddstor/DEVICE_DSM_DEFINITION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _DEVICE_DSM_DEFINITION
---

# _DEVICE_DSM_DEFINITION structure


## -description

The DEVICE_DSM_DEFINITION structure contains the properties for a data set management (DSM) action.

## -struct-fields

### -field Action

**DeviceDsmDefinition_*Xxx*** value that specifies the action to be performed. See [DEVICE_DSM_ACTION Descriptions](/windows-hardware/drivers/storage/device-dsm-action-descriptions) for a list of action values and their associated definition values. These values are defined in *ntddstor.h*.

### -field SingleRange

Specifies whether the DSM action supports only a single range at a time. If the DSM action is to be performed on the entire data set range, the flag DEVICE_DSM_FLAG_ENTIRE_DATA_SET_RANGE is set.

### -field ParameterBlockAlignment

The alignment for the parameter block within the payload of the [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md) request.

### -field ParameterBlockLength

The length, in bytes, of the parameter block within the payload of the IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request. The parameter block will follow the [DSM_DEVICE_INPUT](./ns-ntddstor-_device_manage_data_set_attributes.md) structure. If **ParameterBlockLength** is set to zero, then the parameter block does not exist.

### -field HasOutput

Set TRUE if the action specified in the **Action** member will return output; otherwise, set this to FALSE.

### -field OutputBlockAlignment

The alignment for the output block within the payload of the IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request.

### -field OutputBlockLength

Specifies the length, in bytes, of the output block within the payload of the IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request. The output block follows the DSM_DEVICE_OUTPUT structure. If **OutputBlockLength** is set to zero, then the output block does not exist.

## -remarks

Each DSM action has a definition associated with it. For example, **DeviceDsmAction_Trim** has **DeviceDsmDefinition_Trim** as its associated definition. The DSM sender or handler allocates and initializes the DEVICE_DSM_DEFINITION structure with the appropriate definition. They then pass the pointer to this structure to all DSM-related functions that need it.

See [Data Set Management Overview](/windows-hardware/drivers/storage/data-set-management-overview) for information on how a DSM is processed.

## -see-also

[Data Set Management Overview](/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_ACTION Descriptions](/windows-hardware/drivers/storage/device-dsm-action-descriptions)

[DSM_DEVICE_INPUT](./ns-ntddstor-_device_manage_data_set_attributes.md)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md)
