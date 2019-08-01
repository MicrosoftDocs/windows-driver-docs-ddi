---
UID: NF:ntddstor.DeviceDsmOutputBlock
title: DeviceDsmOutputBlock function (ntddstor.h)
description: The DeviceDsmOutputBlock function gets the output block of a DEVICE_DSM_OUTPUT structure.
tech.root: storage
ms.assetid: a33581ae-15ac-4957-99a0-58ed8c8dbd24
ms.date: 07/31/2019
ms.topic: function
f1_keywords:
 - "ntddstor/DeviceDsmOutputBlock"
ms.keywords: DeviceDsmOutputBlock
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
- DeviceDsmOutputBlock
product:
- Windows
targetos: Windows

---

# DeviceDsmOutputBlock function

## -description

The **DeviceDsmOutputBlock** function gets the output block from the output buffer.

## -parameters

### -param Output

Pointer to the [DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure.

## -returns

Returns a pointer to the output block that immediately follows the DEVICE_DSM_OUTPUT structure.

## -remarks

## -see-also

[DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md)