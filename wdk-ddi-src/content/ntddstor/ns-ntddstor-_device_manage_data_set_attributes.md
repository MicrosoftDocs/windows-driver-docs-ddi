---
UID: NS:ntddstor._DEVICE_MANAGE_DATA_SET_ATTRIBUTES
title: _DEVICE_MANAGE_DATA_SET_ATTRIBUTES (ntddstor.h)
description: The DEVICE DSM_INPUT (or DEVICE_MANAGE_DATA_SET_ATTRIBUTES) structure specifies a management action for the data-set attributes for a device.
old-location: storage\device_manage_data_set_attributes.htm
tech.root: storage
ms.assetid: be0bfcef-09df-4259-a034-0d51db9819ce
ms.date: 08/23/2019
keywords: ["DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure"]
ms.keywords: "DEVICE_DSM_INPUT, PDEVICE_DSM_INPUT, *PDEVICE_MANAGE_DATA_SET_ATTRIBUTES, DEVICE_DSM_FLAG_ENTIRE_DATA_SET_RANGE, DEVICE_MANAGE_DATA_SET_ATTRIBUTES, DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure [Storage Devices], DeviceDsmActionFlag_NonDestructive, PDEVICE_MANAGE_DATA_SET_ATTRIBUTES, PDEVICE_MANAGE_DATA_SET_ATTRIBUTES structure pointer [Storage Devices], _DEVICE_MANAGE_DATA_SET_ATTRIBUTES, ntddstor/DEVICE_MANAGE_DATA_SET_ATTRIBUTES, ntddstor/PDEVICE_MANAGE_DATA_SET_ATTRIBUTES, storage.device_manage_data_set_attributes, structs-general_f8d2d431-7187-4532-ac05-69868909fc66.xml"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: DEVICE_MANAGE_DATA_SET_ATTRIBUTES, *PDEVICE_MANAGE_DATA_SET_ATTRIBUTES
f1_keywords:
 - _DEVICE_MANAGE_DATA_SET_ATTRIBUTES
 - ntddstor/_DEVICE_MANAGE_DATA_SET_ATTRIBUTES
 - PDEVICE_MANAGE_DATA_SET_ATTRIBUTES
 - ntddstor/PDEVICE_MANAGE_DATA_SET_ATTRIBUTES
 - DEVICE_MANAGE_DATA_SET_ATTRIBUTES
 - ntddstor/DEVICE_MANAGE_DATA_SET_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - DEVICE_MANAGE_DATA_SET_ATTRIBUTES
---

# _DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure


## -description

The **DEVICE_DSM_INPUT** (or DEVICE_MANAGE_DATA_SET_ATTRIBUTES) structure specifies a management action for the data-set attributes for a device.

## -struct-fields

### -field Size

Size of the DEVICE_DSM_INPUT structure, in bytes. The value of this member will change as members are added to the structure.

### -field Action

A DEVICE_DSM_ACTION value that specifies the action to be performed. See [DEVICE_DSM_ACTION Descriptions](/windows-hardware/drivers/storage/device-dsm-action-descriptions) for a list of action values and descriptions.

If the **DeviceDsmActionFlag_NonDestructive** flag (most significant bit) is set in **Action**, the specified action is nondestructive. For nondestructive actions, the driver can safely forward the [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md) request to the next lower driver in the stack even if the driver does not handle the specified action. If the driver does handle the DSM, it should perform the normal processing of the data set ranges block that is specified by the **DataSetRangesOffset** and **DataSetRangesLength** members before forwarding the IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request to the next lower driver.

### -field Flags

These flags are global to all control actions. This member can be set to one of the following flags:

| Flag Value | Meaning |
| ---------- | ------- |
| DEVICE_DSM_FLAG_ENTIRE_DATA_SET_RANGE | The control action is specified for the entire block of data set ranges. If this flag is set, the **DataSetRangesOffset** and **DataSetRangesLength** members must be set to zero. |

### -field ParameterBlockOffset

Specifies the start of the parameter block within the payload of the [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md) request. The format of the parameter block depends on the value of the **Action** member. For more information regarding parameter block format, see [DEVICE_DSM_ACTION Descriptions](/windows-hardware/drivers/storage/device-dsm-action-descriptions). **Note**: The offset of the parameter block must be aligned on the address boundary of the corresponding parameter.

If **ParameterBlockOffset** is set to zero, then the parameter block does not exist.

### -field ParameterBlockLength

Specifies the length, in bytes, of the parameter block within the payload of the IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request.

If **ParameterBlockLength** is set to zero, then the parameter block does not exist.

### -field DataSetRangesOffset

Specifies the start of the block of data set ranges within the payload of the IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request. This block consists of one or more contiguous entries that are formatted as [DEVICE_DSM_RANGE](./ns-ntddstor-_device_data_set_range.md) structures. **Note**:  The offset of the data set range block must be aligned on the address boundary of the DEVICE_DSM_RANGE structure.

If set to zero, then the block of data set ranges does not exist.

### -field DataSetRangesLength

Specifies the length, in bytes, of the block of data set ranges within the payload of the IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request. If **DataSetRangesLength** is set to zero, the block of data set ranges does not exist.

## -remarks

For more information on the format of the payload for an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md) request, see [Data Set Management Overview](/windows-hardware/drivers/storage/data-set-management-overview). The total size of the buffer should be at least ```sizeof(DEVICE_DSM_INPUT) + ParameterBlockLength + DataSetRangesLength```.

The block of data set ranges is specified by the **DataSetRangesOffset** and **DataSetRangesLength** members. If this block exists, it contains contiguous [DEVICE_DSM_RANGE](./ns-ntddstor-_device_data_set_range.md) structures.

## -see-also

[Data Set Management Overview](/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_ACTION Descriptions](/windows-hardware/drivers/storage/device-dsm-action-descriptions)

[DEVICE_DSM_RANGE](./ns-ntddstor-_device_data_set_range.md)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md)