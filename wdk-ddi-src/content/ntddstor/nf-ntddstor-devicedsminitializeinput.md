---
UID: NF:ntddstor.DeviceDsmInitializeInput
title: DeviceDsmInitializeInput function
description: The DeviceDsmInitializeInput function initializes a DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure.
ms.assetid: 4a212a8e-1bd1-4ad1-9da1-f9527a304e81
ms.date: 04/11/2018
ms.topic: function
ms.keywords: DeviceDsmInitializeInput
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
-	apiref
api_type: 
-	DllExport
api_location: 
-	NtosKrnl.exe
api_name: 
-	DeviceDsmInitializeInput
product:
-	Windows
targetos: Windows

---

# DeviceDsmInitializeInput function


## -description

The DeviceDsmInitializeInput function initializes a [**DEVICE_MANAGE_DATA_SET_ATTRIBUTES**](ns-ntddstor-_device_manage_data_set_attributes.md) structure.

## -parameters

### -param Definition

A pointer to a DEVICE_DSM_DEFINITION structure that contains parameter block alignment information.

### -param Input

A pointer to the input [**DEVICE_MANAGE_DATA_SET_ATTRIBUTES**](ns-ntddstor-_device_manage_data_set_attributes.md) structure.

### -param InputLength

The length, in bytes, to write to the input.

### -param Flags

Flags for global control actions for the input.

### -param Parameters

Parameters for initializing the parameter block of the input structure.

### -param ParameterBlockLength

The length, in bytes, of the parameter block.

## -returns

This function does not return a value.

## -remarks

## -see-also
