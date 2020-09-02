---
UID: NF:ntddstor.DeviceDsmNumberOfDataSetRanges
title: DeviceDsmNumberOfDataSetRanges function (ntddstor.h)
description: The DeviceDsmNumberOfDataSetRanges function gets the number of data set ranges in the payload of an IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request.
tech.root: storage
ms.assetid: 04c83255-8f92-4db7-848b-928fcc16bb60
ms.date: 08/23/2019
keywords: ["DeviceDsmNumberOfDataSetRanges function"]
ms.keywords: DeviceDsmNumberOfDataSetRanges
req.header: ntddstor.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: 
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
 - DeviceDsmNumberOfDataSetRanges
 - ntddstor/DeviceDsmNumberOfDataSetRanges
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - DeviceDsmNumberOfDataSetRanges
---

# DeviceDsmNumberOfDataSetRanges function


## -description

The **DeviceDsmNumberOfDataSetRanges** function gets the number of data set ranges in the payload of an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes) request.

## -parameters

### -param Input

Pointer to a [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure.

## -returns

**DeviceDsmNumberOfDataSetRanges** returns the number of data set ranges in the payload. Each range is **sizeof**([DEVICE_DSM_RANGE](ns-ntddstor-_device_data_set_range.md)).

## -remarks

See [Data Set Management](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview) for details on how to process a DSM.

## -see-also

[Data Set Management](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md)

[DEVICE_DSM_RANGE](ns-ntddstor-_device_data_set_range.md)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes)

