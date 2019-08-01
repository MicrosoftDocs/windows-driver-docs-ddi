---
UID: NF:ntddstor.DeviceDsmValidateInput
title: DeviceDsmValidateInput function (ntddstor.h)
description: The DeviceDsmValidateInput function validates whether a DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure is valid.
tech.root: storage
ms.assetid: dab84969-6432-4730-b06e-b7bbf7a07f2d
ms.date: 07/31/2019
ms.topic: function
f1_keywords:
 - "ntddstor/DeviceDsmValidateInput"
ms.keywords: DeviceDsmValidateInput
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
- DeviceDsmValidateInput
product:
- Windows
targetos: Windows

---

# DeviceDsmValidateInput function

## -description

The **DeviceDsmValidateInput** function validates whether a [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure is valid.

## -parameters

### -param Definition

Pointer to an opaque [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that contains information about the parameter block alignment and length.

### -param Input

Pointer to the DEVICE_DSM_INPUT structure.

### -param InputLength

The length, in bytes, of the structure to which *Input* points.

## -returns

Returns **TRUE** if the DEVICE_DSM_INPUT structure is valid, or **FALSE** otherwise.

## -remarks

## -see-also

[DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md)
