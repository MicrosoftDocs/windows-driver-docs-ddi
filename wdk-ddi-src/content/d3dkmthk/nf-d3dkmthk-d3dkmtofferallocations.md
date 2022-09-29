---
UID: NF:d3dkmthk.D3DKMTOfferAllocations
title: D3DKMTOfferAllocations function (d3dkmthk.h)
description: The D3DKMTOfferAllocations function offers video memory allocations for reuse. The function returns STATUS_SUCCESS if allocations were successfully offered.
old-location: display\d3dkmtofferallocations.htm
ms.date: 02/25/2022
keywords: ["D3DKMTOfferAllocations function"]
ms.keywords: D3DKMTOfferAllocations, D3DKMTOfferAllocations callback function [Display Devices], PFND3DKMT_OFFERALLOCATIONS, PFND3DKMT_OFFERALLOCATIONS callback, d3dkmthk/D3DKMTOfferAllocations, display.d3dkmtofferallocations
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTOfferAllocations
 - d3dkmthk/D3DKMTOfferAllocations
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTOfferAllocations
---

# D3DKMTOfferAllocations function

## -description

Offers video memory allocations for reuse.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_OFFERALLOCATIONS](ns-d3dkmthk-_d3dkmt_offerallocations.md) structure that defines memory allocations that the driver offers for reuse.

## -returns

Returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The allocations were successfully offered. |
| STATUS_DEVICE_REMOVED | The graphics adapter was stopped or the display device was reset. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

## -see-also

[D3DKMTReclaimAllocations](nf-d3dkmthk-d3dkmtreclaimallocations.md)

[D3DKMT_OFFERALLOCATIONS](ns-d3dkmthk-_d3dkmt_offerallocations.md)
