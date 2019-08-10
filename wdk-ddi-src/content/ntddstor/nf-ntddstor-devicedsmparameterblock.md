---
UID: NF:ntddstor.DeviceDsmParameterBlock
title: DeviceDsmParameterBlock function (ntddstor.h)
description: The DeviceDsmParameterBlock function gets the parameter block for a DEVICE_DSM_INPUT structure.
tech.root: storage
ms.assetid: 60c25727-7218-4b5e-935f-fb34fe926da5
ms.date: 08/15/2019
ms.topic: function
f1_keywords:
 - "ntddstor/DeviceDsmParameterBlock"
ms.keywords: DeviceDsmParameterBlock
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
- DeviceDsmParameterBlock
product:
- Windows
targetos: Windows

---

# DeviceDsmParameterBlock function

## -description

The **DeviceDsmParameterBlock** function gets the parameter block associated with a [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure.

## -parameters

### -param Input

Pointer to a DEVICE_DSM_INPUT structure.

## -returns

Returns a pointer to the parameter block that immediately follows the DEVICE_DSM_INPUT structure.

## -remarks

## -see-also

[DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md)
