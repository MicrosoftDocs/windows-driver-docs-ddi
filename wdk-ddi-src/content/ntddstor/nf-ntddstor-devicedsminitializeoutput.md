---
UID: NF:ntddstor.DeviceDsmInitializeOutput
title: DeviceDsmInitializeOutput function (ntddstor.h)
description: The DeviceDsmInitializeOutput function initializes a DEVICE_DSM_OUTPUT structure.
tech.root: storage
ms.assetid: e68acc49-63c9-4ea2-9450-fa45dd2b5e06
ms.date: 08/23/2019
ms.topic: function
f1_keywords:
 - "ntddstor/DeviceDsmInitializeOutput"
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

The **DeviceDsmInitializeOutput** function initializes a [DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure.

## -parameters

### -param Definition

Pointer to a [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that defines the data set management (DSM) operation.

### -param Output

Pointer to the [DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure to be initialized.

### -param OutputLength

The length, in bytes, of the entire output buffer.

### -param Flags

Flags for the DSM action in the DEVICE_DSM_OUTPUT structure.

## -returns

This function does not return a value.

## -remarks

See [Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview) for information on how to process a DSM.

## -see-also

[Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md)

[DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md)
