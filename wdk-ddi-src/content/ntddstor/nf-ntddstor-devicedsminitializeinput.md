---
UID: NF:ntddstor.DeviceDsmInitializeInput
title: DeviceDsmInitializeInput function (ntddstor.h)
description: The DeviceDsmInitializeInput function initializes a DEVICE_DSM_INPUT structure.
ms.assetid: 4a212a8e-1bd1-4ad1-9da1-f9527a304e81
tech.root: storage
ms.date: 08/23/2019
keywords: ["DeviceDsmInitializeInput function"]
f1_keywords:
 - "ntddstor/DeviceDsmInitializeInput"
 - "DeviceDsmInitializeInput"
ms.keywords: DeviceDsmInitializeInput
req.header: ntddstor.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- DeviceDsmInitializeInput
targetos: Windows

---

# DeviceDsmInitializeInput function

## -description

The **DeviceDsmInitializeInput** function initializes the [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure and parameter block, if any, of a data set management (DSM) operation.

## -parameters

### -param Definition

Pointer to a [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that defines the action.

### -param Input

Pointer to a caller-allocated [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) input structure.

### -param InputLength

The length, in bytes, of the entire input buffer for the [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes) request.

### -param Flags

Flags for global control actions for the input. This value can be one of the DEVICE_DSM_FLAG_*XXX* values defined in *ntddstor.h*.

### -param Parameters

Parameters for initializing the parameter block of the input structure. The format of the parameter block depends on the action defined by *Definition*. See [DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions) for a list of actions and their parameter block formats.

### -param ParameterBlockLength

The length, in bytes, of the parameter block. If the action defined by *Definition* does not have parameters, *ParameterBlockLength* is set to zero.

## -remarks

To add a data set range to the input operation, call [**DeviceDsmAddDataSetRange**](nf-ntddstor-devicedsmadddatasetrange.md).

See [Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview) for information on how to set up and process a DSM action.

## -see-also

[Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions)

[DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md)

[**DeviceDsmAddDataSetRange**](nf-ntddstor-devicedsmadddatasetrange.md)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes)
