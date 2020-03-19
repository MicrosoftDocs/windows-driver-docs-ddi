---
UID: NS:dispmprt._DXGK_VIRTUALGPUMEMORYRESOURCE
title: _DXGK_VIRTUALGPUMEMORYRESOURCE
author: windows-driver-content
description: Virtual GPU memory resource.
tech.root: display
ms.assetid: c3a78863-0715-4051-9ae1-145bbc2746c6
ms.author: windowsdriverdev
ms.date: 04/04/2019 
keywords: ["_DXGK_VIRTUALGPUMEMORYRESOURCE structure"]
f1_keywords:
 - "dispmprt/_DXGK_VIRTUALGPUMEMORYRESOURCE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_VIRTUALGPUMEMORYRESOURCE, DXGK_VIRTUALGPUMEMORYRESOURCE, *PDXGK_VIRTUALGPUMEMORYRESOURCE, 
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
req.typenames: DXGK_VIRTUALGPUMEMORYRESOURCE, *PDXGK_VIRTUALGPUMEMORYRESOURCE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGK_VIRTUALGPUMEMORYRESOURCE
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# _DXGK_VIRTUALGPUMEMORYRESOURCE structure

## -description

Virtual GPU memory resource.

## -struct-fields

### -field DriverAllocationHandle

The driver allocation handle.

### -field AllocationAddress

The physical address of the allocation, which include the driver memory segment ID and the segment offset.

### -field AllocationSize
 
Allocation size in bytes.

## -remarks

## -see-also
