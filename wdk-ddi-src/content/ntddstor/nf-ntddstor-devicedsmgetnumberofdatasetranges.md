---
UID: NF:ntddstor.DeviceDsmGetNumberOfDataSetRanges
title: DeviceDsmGetNumberOfDataSetRanges function (ntddstor.h)
description: The DeviceDsmGetNumberOfDataSetRanges function gets the number of data set ranges in a given input length.
tech.root: storage
ms.assetid: a53b0fcc-7286-4d65-b4a0-d46b505073e7
ms.date: 07/31/2019
ms.topic: function
f1_keywords:
 - "ntddstor/DeviceDsmGetNumberOfDataSetRanges"
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

The **DeviceDsmGetNumberOfDataSetRanges** function gets the number of data set ranges in a given input operation.

## -parameters

### -param Definition

Pointer to an opaque [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that contains parameter block alignment and length information.

### -param InputLength

The length, in bytes, of the input buffer.

### -param ParameterBlockLength

The length, in bytes, of a parameter block.

## -returns

Returns the number of data set ranges in the given input length.

## -remarks

A DSM operation handler calls **DeviceDsmGetNumberOfDataSetRanges** to determine the number of data set ranges in the operation's input length.

## -see-also
