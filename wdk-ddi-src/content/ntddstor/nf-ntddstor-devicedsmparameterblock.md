---
UID: NF:ntddstor.DeviceDsmParameterBlock
title: DeviceDsmParameterBlock function (ntddstor.h)
description: The DeviceDsmParameterBlock function gets the parameter block for a data set management (DSM) operation.
tech.root: storage
ms.assetid: 60c25727-7218-4b5e-935f-fb34fe926da5
ms.date: 08/23/2019
keywords: ["DeviceDsmParameterBlock function"]
ms.keywords: DeviceDsmParameterBlock
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
 - DeviceDsmParameterBlock
 - ntddstor/DeviceDsmParameterBlock
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - DeviceDsmParameterBlock
---

# DeviceDsmParameterBlock function


## -description

The **DeviceDsmParameterBlock** function gets the parameter block for a data set management (DSM) operation.

## -parameters

### -param Input

Pointer to a [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure.

## -returns

**DeviceDsmParameterBlock** returns a pointer to the parameter block that immediately follows the DEVICE_DSM_INPUT structure.

## -remarks

The DSM handler calls this function only if the members of *Input* indicate that the operation has a parameter block. See [Data Set Management](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview) for details on how to process a DSM.

## -see-also

[Data Set Management](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md)

