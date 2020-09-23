---
UID: NF:ntddstor.DeviceDsmGetNumberOfDataSetRanges
title: DeviceDsmGetNumberOfDataSetRanges function (ntddstor.h)
description: The DeviceDsmGetNumberOfDataSetRanges function gets the number of data set ranges in the payload of an IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request.
tech.root: storage
ms.assetid: a53b0fcc-7286-4d65-b4a0-d46b505073e7
ms.date: 08/23/2019
keywords: ["DeviceDsmGetNumberOfDataSetRanges function"]
ms.keywords: DeviceDsmGetNumberOfDataSetRanges
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
targetos: Windows
f1_keywords:
 - DeviceDsmGetNumberOfDataSetRanges
 - ntddstor/DeviceDsmGetNumberOfDataSetRanges
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - DeviceDsmGetNumberOfDataSetRanges
---

# DeviceDsmGetNumberOfDataSetRanges function


## -description

The **DeviceDsmGetNumberOfDataSetRanges** function gets the number of data set ranges required for the specified data set management (DSM) operation.

## -parameters

### -param Definition

Pointer to a [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that defines the operation.

### -param InputLength

The length, in bytes, of the entire input buffer.

### -param ParameterBlockLength

The length, in bytes, of a parameter block.

## -returns

**DeviceDsmGetNumberOfDataSetRanges** returns the number of data set ranges required for the specified operation. Each range is **sizeof**([DEVICE_DSM_RANGE](ns-ntddstor-_device_data_set_range.md)).

## -remarks

See [Data Set Management](/windows-hardware/drivers/storage/data-set-management-overview) for details on how to process a DSM.

## -see-also

[Data Set Management](/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md)

[DEVICE_DSM_RANGE](ns-ntddstor-_device_data_set_range.md)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md)