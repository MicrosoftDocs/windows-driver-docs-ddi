---
UID: NF:storport.StorPortGetMessageInterruptIDFromProcessorIndex
tech.root: storage
title: StorPortGetMessageInterruptIDFromProcessorIndex
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the StorPortGetMessageInterruptIDFromProcessorIndex function.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortGetMessageInterruptIDFromProcessorIndex
f1_keywords:
 - StorPortGetMessageInterruptIDFromProcessorIndex
 - storport/StorPortGetMessageInterruptIDFromProcessorIndex
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortGetMessageInterruptIDFromProcessorIndex
---

## -description

A Storport miniport can call **StorPortGetMessageInterruptIDFromProcessorIndex** to get the message interrupt ID of the specified processor index.

## -parameters

### -param HwDeviceExtension

[in] Pointer to the miniport's device extension.

### -param ProcessorIndex

[in] A system-wide processor index. If a multiprocessor system contains a total of *n* logical processors, valid processor indexes range from 0 to *n*-1.

### -param MessageInterruptID

[out] Pointer to a ULONG value in which the message interrupt ID of **ProcessorIndex** is written.

## -returns

**StorPortGetMessageInterruptIDFromProcessorIndex** returns STOR_STATUS_SUCCESS if the miniport data is successfully reported. Possible error return values include the following.

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_INVALID_PARAMETER | There is an invalid parameter, such as an invalid **ProcessorIndex** value. |
| STOR_STATUS_UNSUCCESSFUL      | An error occurred for internal reasons. |

## -remarks

See the *Remarks* section of [**KeGetProcessorNumberFromIndex**](../wdm/nf-wdm-kegetprocessornumberfromindex.md) for details.
