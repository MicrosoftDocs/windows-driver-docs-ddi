---
UID: NF:ntddstor.DeviceDsmNumberOfDataSetRanges
title: DeviceDsmNumberOfDataSetRanges function (ntddstor.h)
description: The DeviceDsmNumberOfDataSetRanges function gets the number of data set ranges for a DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure.
tech.root: storage
ms.assetid: 04c83255-8f92-4db7-848b-928fcc16bb60
ms.date: 07/31/2019
ms.topic: function
f1_keywords:
 - "ntddstor/DeviceDsmNumberOfDataSetRanges"
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
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- DeviceDsmNumberOfDataSetRanges
product:
- Windows
targetos: Windows

---

# DeviceDsmNumberOfDataSetRanges function

## -description

The **DeviceDsmNumberOfDataSetRanges** function gets the number of data set ranges in the input operation identified by a [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure.

## -parameters

### -param Input

Pointer to the [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure.

## -returns

Returns the number of data set ranges in the input operation identified by the DEVICE_DSM_ATTRIBUTES structure.

## -remarks

## -see-also

[DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md)
