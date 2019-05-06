---
UID: NF:ntddstor.DeviceDsmGetNumberOfDataSetRanges
title: DeviceDsmGetNumberOfDataSetRanges function (ntddstor.h)
description: The DeviceDsmGetNumberOfDataSetRanges function gets the number of data set ranges in a given input length.
tech.root: storage
ms.assetid: a53b0fcc-7286-4d65-b4a0-d46b505073e7
ms.date: 04/11/2018
ms.topic: function
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
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- DeviceDsmGetNumberOfDataSetRanges
product:
- Windows
targetos: Windows

---

# DeviceDsmGetNumberOfDataSetRanges function


## -description

The **DeviceDsmGetNumberOfDataSetRanges** function gets the number of data set ranges in a given input length.

## -parameters

### -param Definition

A pointer to a DEVICE_DSM_DEFINITION structure that contains parameter block alignment information.

### -param InputLength

The length, in bytes, of the input buffer.

### -param ParameterBlockLength

The length, in bytes, of a parameter block.

## -returns

Returns the number data set ranges in the given input length.

## -remarks

## -see-also
