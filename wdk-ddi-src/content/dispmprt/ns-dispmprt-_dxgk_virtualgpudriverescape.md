---
UID: NS:dispmprt._DXGK_VIRTUALGPUDRIVERESCAPE
title: _DXGK_VIRTUALGPUDRIVERESCAPE
author: windows-driver-content
description: Information to be passed between a user mode emulation DLL and the kernel mode driver.
tech.root: display
ms.assetid: ef42bc4c-4ed2-40bf-9548-1de05ff6718f
ms.author: windowsdriverdev
ms.date: 04/04/2019 
f1_keywords:
 - "dispmprt/_DXGK_VIRTUALGPUDRIVERESCAPE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_VIRTUALGPUDRIVERESCAPE, DXGK_VIRTUALGPUDRIVERESCAPE, *PDXGK_VIRTUALGPUDRIVERESCAPE, 
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGK_VIRTUALGPUDRIVERESCAPE, *PDXGK_VIRTUALGPUDRIVERESCAPE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGK_VIRTUALGPUDRIVERESCAPE
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# _DXGK_VIRTUALGPUDRIVERESCAPE structure

## -description

Information to be passed between a user mode emulation DLL and the kernel mode driver.

## -struct-fields

### -field PartitionId

Identifies the vGPU partition if needed.

### -field InputBufferSize

The size in bytes of the buffer, *pInputBuffer* points to.

### -field OutputBufferSize

The size in bytes of the buffer, *pOutputBuffe*r points to.

### -field pInputBuffer

Pointer to the input buffer. This is the pointer to the GPUP_DRIVER_ESCAPE_INPUT, which is followed by the driver data.

### -field pOutputBuffer

Pointer to the output buffer.

## -remarks

The pointers to the input and output buffers cannot be the same.

## -see-also
