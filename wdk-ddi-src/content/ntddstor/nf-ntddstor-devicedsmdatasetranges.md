---
UID: NF:ntddstor.DeviceDsmDataSetRanges
title: DeviceDsmDataSetRanges function (ntddstor.h)
description: The DeviceDsmDataSetRanges function function gets a pointer to the data set ranges associated with a DEVICE_DSM_INPUT structure.
tech.root: storage
ms.assetid: 0a7044a8-4cf1-4e40-92e1-c0dacea99ea9
ms.date: 08/23/2019
keywords: ["DeviceDsmDataSetRanges function"]
ms.keywords: DeviceDsmDataSetRanges
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
 - DeviceDsmDataSetRanges
 - ntddstor/DeviceDsmDataSetRanges
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - DeviceDsmDataSetRanges
---

# DeviceDsmDataSetRanges function


## -description

The **DeviceDsmDataSetRanges** function gets a pointer to the data set ranges for a data set management (DSM) operation.

## -parameters

### -param Input

Pointer to the [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure.

## -returns

**DeviceDsmDataSetRanges** returns a pointer to the first [DEVICE_DSM_RANGE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_data_set_range) structure in the data set range.

## -remarks

The DSM handler calls this function only if the members of *Input* indicate that the operation has range data. See [Data Set Management](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview) for details on how to process a DSM.

## -see-also

[Data Set Management](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md)

[DEVICE_DSM_RANGE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_data_set_range)

