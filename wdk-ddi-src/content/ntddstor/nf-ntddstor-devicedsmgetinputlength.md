---
UID: NF:ntddstor.DeviceDsmGetInputLength
title: DeviceDsmGetInputLength function (ntddstor.h)
description: The DeviceDsmGetInputLength function gets the number of bytes in a DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure.
tech.root: storage
ms.assetid: 689bb265-239d-442c-b2ae-be648cf8d641
ms.date: 04/11/2018
ms.topic: function
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
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- DeviceDsmGetInputLength
product:
- Windows
targetos: Windows

---

# DeviceDsmGetInputLength function


## -description

The **DeviceDsmGetInputLength** function gets the number of bytes in a data set management input operation.

## -parameters

### -param Definition

A pointer to a DEVICE_DSM_DEFINITION structure that contains parameter block alignment and length information.

### -param ParameterBlockLength

The length, in bytes, of a parameter block.

### -param NumberOfDataSetRanges

The number of data set ranges in the [**DEVICE_MANAGE_DATA_SET_ATTRIBUTES**](ns-ntddstor-_device_manage_data_set_attributes.md) structure.

## -returns

Returns the number of bytes in the input: the length of a [**DEVICE_MANAGE_DATA_SET_ATTRIBUTES**](ns-ntddstor-_device_manage_data_set_attributes.md) structure, the length of the parameter block, and the length of all data set ranges.

## -remarks

## -see-also
