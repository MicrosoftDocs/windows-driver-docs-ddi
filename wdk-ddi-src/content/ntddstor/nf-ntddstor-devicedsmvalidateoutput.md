---
UID: NF:ntddstor.DeviceDsmValidateOutput
title: DeviceDsmValidateOutput function (ntddstor.h)
description: The DeviceDsmValidateOutput function validates a DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT structure.
ms.assetid: 322aad6f-62d2-4530-be13-c3f8f64a1a26
ms.date: 04/11/2018
ms.topic: function
ms.keywords: DeviceDsmValidateOutput
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
-	DeviceDsmValidateOutput
product:
-	Windows
targetos: Windows

---

# DeviceDsmValidateOutput function


## -description

The **DeviceDsmValidateOutput** function validates a [**DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT**](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure.

## -parameters

### -param Definition

A pointer to a DEVICE_DSM_DEFINITION structure that contains output block length and alignment information.

### -param Output

A pointer to the [**DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT**](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure to be validated.

### -param OutputLength

The length, in bytes, of the output.

## -returns

Returns TRUE if the [**DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT**](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure is valid, or FALSE otherwise.

## -remarks

## -see-also
