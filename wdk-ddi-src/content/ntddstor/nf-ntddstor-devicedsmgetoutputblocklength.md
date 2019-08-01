---
UID: NF:ntddstor.DeviceDsmGetOutputBlockLength
title: DeviceDsmGetOutputBlockLength function (ntddstor.h)
description: The DeviceDsmGetOutputBlockLength function gets the length, in bytes, of an output block.
tech.root: storage
ms.assetid: 57512e92-810a-423e-98c0-be892cc81c88
ms.date: 07/31/2019
ms.topic: function
f1_keywords:
 - "ntddstor/DeviceDsmGetOutputBlockLength"
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
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- DeviceDsmGetOutputBlockLength
product:
- Windows
targetos: Windows

---

# DeviceDsmGetOutputBlockLength function

## -description

The **DeviceDsmGetOutputBlockLength** function gets the length, in bytes, of a data set management (DSM) output block.

## -parameters

### -param Definition

Pointer to an opaque [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that contains parameter block alignment and length information.

### -param OutputLength

The length, in bytes, of the entire output (the [**DEVICE_DSM_OUTPUT**](ns-ntddstor-_device_manage_data_set_attributes_output.md) output buffer plus the output block).

## -returns

Returns the length, in bytes, of the output block.

## -remarks

## -see-also

[**DEVICE_DSM_OUTPUT**](ns-ntddstor-_device_manage_data_set_attributes_output.md)