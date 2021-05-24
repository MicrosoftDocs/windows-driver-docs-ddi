---
UID: NF:storport.StorPortMaskMsixInterrupt
tech.root: storage
title: StorPortMaskMsixInterrupt
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: StorPortMaskMsixInterrupt masks or unmasks the specified MSI-X interrupt.
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
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
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
 - StorPortMaskMsixInterrupt
f1_keywords:
 - StorPortMaskMsixInterrupt
 - storport/StorPortMaskMsixInterrupt
dev_langs:
 - c++
---

## -description

**StorPortMaskMsixInterrupt** masks or unmasks an interrupt in the MSI-X hardware interrupt table.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the miniport's device extension.

### -param MessageId

[in] The index of the table entry in the MSI-X hardware interrupt table.

### -param Mask

[in] Indicates whether to mask (TRUE) or unmask (FALSE) the interrupt.

## -returns

This function returns one of the following status codes.

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The specified MSI-X interrupt was successfully enabled/disabled. |
| STOR_STATUS_INVALID_PARAMETER | A parameter is invalid; for example, **MessageId** is not a valid table index value. |
| STOR_STATUS_UNSUCCESSFUL | Returned for other internal system reasons. |

## -remarks

A miniport can call **StorPortMaskMsixInterrupt** to mask or unmask the specified interrupt in the MSI-X hardware interrupt table. If a table entry is masked, the device does not generate interrupts that correspond to that table entry.
