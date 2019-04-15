---
UID: NF:ntddstor.DeviceDsmInitializeOutput
title: DeviceDsmInitializeOutput function (ntddstor.h)
description: The DeviceDsmInitializeOutput function initializes a DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT structure.
ms.assetid: e68acc49-63c9-4ea2-9450-fa45dd2b5e06
ms.date: 04/11/2018
ms.topic: function
ms.keywords: DeviceDsmInitializeOutput
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
- DeviceDsmInitializeOutput
product:
- Windows
targetos: Windows

---

# DeviceDsmInitializeOutput function


## -description

The **DeviceDsmInitializeOutput** function initializes a [**DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT**](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure.

## -parameters

### -param Definition

A pointer to a DEVICE_DSM_DEFINITION structure that contains output block alignment and length information.

### -param Output

A pointer to the [**DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT**](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure to be initialized.

### -param OutputLength

The length, in bytes, of the output.

### -param Flags

Flags for the data set management action in the [**DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT**](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure.

## -returns

This function does not return a value.

## -remarks

## -see-also
