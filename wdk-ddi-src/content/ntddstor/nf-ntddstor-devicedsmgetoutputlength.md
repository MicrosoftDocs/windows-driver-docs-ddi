---
UID: NF:ntddstor.DeviceDsmGetOutputLength
title: DeviceDsmGetOutputLength function (ntddstor.h)
description: The DeviceDsmGetOutputLength function gets the length, in bytes, of a data set management output operation.
tech.root: storage
ms.assetid: deb9e6b6-d744-4c3a-a6f4-d1b452401a08
ms.date: 08/23/2019
keywords: ["DeviceDsmGetOutputLength function"]
ms.keywords: DeviceDsmGetOutputLength
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
 - DeviceDsmGetOutputLength
 - ntddstor/DeviceDsmGetOutputLength
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - DeviceDsmGetOutputLength
---

# DeviceDsmGetOutputLength function


## -description

The **DeviceDsmGetOutputLength** function gets the length, in bytes, of the output buffer for a data set management (DSM) operation.

## -parameters

### -param Definition

Pointer to a [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that defines the DSM operation.

### -param OutputBlockLength

The length, in bytes, of the output block.

## -returns

**DeviceDsmGetOutputLength** returns the total number of bytes in the output: the length of a [DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure plus the length of the output block, if any. It returns zero if the operation does not have output.

## -remarks

See [Data Set Management Overview](/windows-hardware/drivers/storage/data-set-management-overview) for information on how to set up and process a DSM action.

## -see-also

[Data Set Management Overview](/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md)

[DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md)