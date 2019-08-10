---
UID: NF:ntddstor.DeviceDsmValidateOutput
title: DeviceDsmValidateOutput function (ntddstor.h)
description: The DeviceDsmValidateOutput function validates a DEVICE_DSM_OUTPUT structure.
tech.root: storage
ms.assetid: 322aad6f-62d2-4530-be13-c3f8f64a1a26
ms.date: 08/15/2019
ms.topic: function
f1_keywords:
 - "ntddstor/DeviceDsmValidateOutput"
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
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- DeviceDsmValidateOutput
product:
- Windows
targetos: Windows

---

# DeviceDsmValidateOutput function

## -description

The **DeviceDsmValidateOutput** function validates a [DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure.

## -parameters

### -param Definition

Pointer to an opaque [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that contains output block alignment and length information.

### -param Output

Pointer to the DEVICE_DSM_OUTPUT structure to be validated.

### -param OutputLength

The length, in bytes, of the structure to which *Output* points.

## -returns

Returns TRUE if the [DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure is valid, or FALSE otherwise.

## -remarks

## -see-also

[**DeviceDsmValidateOutputLength**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/nf-ntddstor-devicedsmvalidateoutputlength)
