---
UID: NF:ntddstor.DeviceDsmValidateOutputLength
title: DeviceDsmValidateOutputLength function
author: windows-driver-content
description: The DeviceDsmValidateOutputLength function validates the length of an output buffer.
tech.root: ntddstor
ms.assetid: 953960c8-dfe1-48d9-9265-08e37a18d0d4
ms.author: windowsdriverdev
ms.date: 07/31/19
ms.topic: function
ms.keywords: DeviceDsmValidateOutputLength
f1_keywords:
 - "ntddstor/DeviceDsmValidateOutputLength"
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
- 
api_location: 
- 
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

Pointer to an opaque [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that contains output block alignment and length information.

### -param OutputLength

Sender-provided value that specifies the length, in bytes, of the sender-provided output buffer.

## -returns

This function returns **TRUE** when the length of the output buffer is valid; otherwise, it returns **FALSE**.

## -remarks

The output buffer includes the DEVICE_DSM_OUTPUT structure plus its associated output block.

## -see-also

[DeviceDsmValidateOutput](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/nf-ntddstor-devicedsmvalidateoutput)
