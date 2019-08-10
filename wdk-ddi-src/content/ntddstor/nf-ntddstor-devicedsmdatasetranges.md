---
UID: NF:ntddstor.DeviceDsmDataSetRanges
title: DeviceDsmDataSetRanges function (ntddstor.h)
description: The DeviceDsmDataSetRanges function sets the data set range in a DEVICE_DSM_RANGE structure.
tech.root: storage
ms.assetid: 0a7044a8-4cf1-4e40-92e1-c0dacea99ea9
ms.date: 08/15/2019
ms.topic: function
f1_keywords:
 - "ntddstor/DeviceDsmDataSetRanges"
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
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- DeviceDsmDataSetRanges
product:
- Windows
targetos: Windows

---

# DeviceDsmDataSetRanges function

## -description

The **DeviceDsmDataSetRanges** function gets a pointer to the data set ranges associated with a [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure.

## -parameters

### -param Input

Pointer to the [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure.

## -returns

Returns a pointer to a [DEVICE_DSM_RANGE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_data_set_range) structure that represents a device data set range.

## -remarks

## -see-also

[DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md)

[DEVICE_DSM_RANGE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_data_set_range)
