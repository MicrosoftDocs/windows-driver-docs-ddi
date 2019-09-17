---
UID: NF:ntddstor.DeviceDsmValidateInput
title: DeviceDsmValidateInput function (ntddstor.h)
description: The DeviceDsmValidateInput function validates whether a DEVICE_DSM_INPUT structure is valid.
tech.root: storage
ms.assetid: dab84969-6432-4730-b06e-b7bbf7a07f2d
ms.date: 08/23/2019
ms.topic: function
f1_keywords:
 - "ntddstor/DeviceDsmValidateInput"
ms.keywords: DeviceDsmValidateInput
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
- DeviceDsmValidateInput
product:
- Windows
targetos: Windows

---

# DeviceDsmValidateInput function

## -description

The **DeviceDsmValidateInput** function validates the input for a data set management (DSM) operation.

## -parameters

### -param Definition

Pointer to a [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that defines the operation.

### -param Input

Pointer to the [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure of the operation.

### -param InputLength

The length, in bytes, of the entire input buffer.

## -returns

Returns **TRUE** if the input is valid, or **FALSE** otherwise.

## -remarks

The input is passed in the payload of an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes) request. Before processing the request, the handler should first call **DeviceDsmValidateInput** to ensure that the input is valid based on the operation's *Definition* and *Input* (whose **Action** members must match), including the DEVICE_DSM_INPUT structure that *Input* points to, and the parameter block and data set ranges, if any, that follow the DEVICE_DSM_INPUT structure.

See [Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview) for more details on handling a DSM.

## -see-also

[Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md)

[DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes)
