---
UID: NF:ntddstor.DeviceDsmGetOutputBlockLength
title: DeviceDsmGetOutputBlockLength function (ntddstor.h)
description: The DeviceDsmGetOutputBlockLength function gets the length, in bytes, of a data set management (DSM) output block.
tech.root: storage
ms.assetid: 57512e92-810a-423e-98c0-be892cc81c88
ms.date: 08/23/2019
keywords: ["DeviceDsmGetOutputBlockLength function"]
ms.keywords: DeviceDsmGetOutputBlockLength
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
 - DeviceDsmGetOutputBlockLength
 - ntddstor/DeviceDsmGetOutputBlockLength
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - DeviceDsmGetOutputBlockLength
---

# DeviceDsmGetOutputBlockLength function


## -description

The **DeviceDsmGetOutputBlockLength** function gets the length, in bytes, of a data set management (DSM) output block.

## -parameters

### -param Definition

Pointer to a [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that defines the operation.

### -param OutputLength

The length, in bytes, of the entire output (the [DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md) output buffer plus the output block).

## -returns

Returns the length, in bytes, of the output block.

## -remarks

See [Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview) for information on how to set up and process a DSM action.

## -see-also

[Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md)

[DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md)

