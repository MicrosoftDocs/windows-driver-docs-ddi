---
UID: NF:ntddstor.DeviceDsmValidateOutput
title: DeviceDsmValidateOutput function (ntddstor.h)
description: The DeviceDsmValidateOutput function validates a DEVICE_DSM_OUTPUT structure.
tech.root: storage
ms.assetid: 322aad6f-62d2-4530-be13-c3f8f64a1a26
ms.date: 08/23/2019
ms.topic: function
f1_keywords:
 - "ntddstor/DeviceDsmValidateOutput"
ms.keywords: DeviceDsmValidateOutput
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
- DeviceDsmValidateOutput
product:
- Windows
targetos: Windows

---

# DeviceDsmValidateOutput function

## -description

The **DeviceDsmValidateOutput** function validates the output for a data set management (DSM) operation.

## -parameters

### -param Definition

Pointer to a [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that defines the operation.

### -param Output

Pointer to the [DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure of the operation.

### -param OutputLength

The length, in bytes, of the entire output buffer.

## -returns

Returns TRUE if the output is valid, or FALSE otherwise.

## -remarks

The output is returned in the payload of an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes) request. Before extracting the output, the caller should first call **DeviceDsmValidateOutput** to ensure that the output is valid based on the operation's *Definition* and *Output* (whose **Action** members must match), including the DEVICE_DSM_OUTPUT structure that *Output* points to, and the output block, if any, that follows the DEVICE_DSM_OUTPUT structure.

See [Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview) for more details on handling a DSM.

## -see-also

[Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md)
