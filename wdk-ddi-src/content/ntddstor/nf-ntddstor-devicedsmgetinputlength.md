---
UID: NF:ntddstor.DeviceDsmGetInputLength
title: DeviceDsmGetInputLength function (ntddstor.h)
description: The DeviceDsmGetInputLength function gets the number of bytes in a DEVICE_DSM_INPUT structure.
tech.root: storage
ms.assetid: 689bb265-239d-442c-b2ae-be648cf8d641
ms.date: 08/23/2019
keywords: ["DeviceDsmGetInputLength function"]
ms.keywords: DeviceDsmGetInputLength
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
 - DeviceDsmGetInputLength
 - ntddstor/DeviceDsmGetInputLength
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - DeviceDsmGetInputLength
---

# DeviceDsmGetInputLength function


## -description

The **DeviceDsmGetInputLength** function calculates the total number of bytes in a data set management (DSM) input operation.

## -parameters

### -param Definition

Pointer to a [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that defines the action.

### -param ParameterBlockLength

The length, in bytes, of the input operation's parameter block. If the input operation has no parameters, *ParameterBlockLength* is set to zero.

### -param NumberOfDataSetRanges

The number of data set ranges associated with the input operation. If the input operation has no data set ranges, *NumberOfDataSetRanges* is set to zero.

## -returns

**DeviceDsmGetInputLength** returns the total number of bytes required for the input operation: the length of the [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure, plus the length of the parameter block (if any), plus the length of all data set ranges (if any).

## -remarks

See [Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview) for information on how to set up and process a DSM action.

## -see-also

[Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md)

[DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md)

