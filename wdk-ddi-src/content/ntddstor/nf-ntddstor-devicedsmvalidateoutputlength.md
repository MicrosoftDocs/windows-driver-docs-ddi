---
UID: NF:ntddstor.DeviceDsmValidateOutputLength
title: DeviceDsmValidateOutputLength function
author: windows-driver-content
description: The DeviceDsmValidateOutputLength function validates the length of an output buffer.
tech.root: storage
ms.assetid: 953960c8-dfe1-48d9-9265-08e37a18d0d4
ms.author: windowsdriverdev
ms.date: 08/23/2019
keywords: ["DeviceDsmValidateOutputLength function"]
ms.keywords: DeviceDsmValidateOutputLength
f1_keywords:
 - "ntddstor/DeviceDsmValidateOutputLength"
 - "DeviceDsmValidateOutputLength"
req.header: ntddstor.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
- HeaderDef
api_location: 
- ntddstor.h
api_name: 
- DeviceDsmValidateOutputLength
product: 
- Windows
targetos: Windows

---

# DeviceDsmValidateOutputLength function

## -description

The **DeviceDsmValidateOutputLength** function validates the length of an output buffer.

## -parameters

### -param Definition

Pointer to a [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that defines the operation.

### -param OutputLength

Length, in bytes, of the output buffer.

## -returns

**DeviceDsmValidateOutputLength** returns **TRUE** when the length of the output buffer is valid; otherwise, it returns **FALSE**.

## -remarks

The output buffer includes the [DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure plus the output block that immediately follows it, if any.

See [Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview) for more details on handling a DSM.

## -see-also

[Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md)

[DEVICE_DSM_OUTPUT](ns-ntddstor-_device_manage_data_set_attributes_output.md)
