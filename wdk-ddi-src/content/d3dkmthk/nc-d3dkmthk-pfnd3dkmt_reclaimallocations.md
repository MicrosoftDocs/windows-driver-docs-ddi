---
UID: NC:d3dkmthk.PFND3DKMT_RECLAIMALLOCATIONS
title: PFND3DKMT_RECLAIMALLOCATIONS (d3dkmthk.h)
description: Reclaims video memory allocations.
old-location: display\d3dkmtreclaimallocations.htm
ms.date: 05/10/2018
keywords: ["PFND3DKMT_RECLAIMALLOCATIONS callback function"]
ms.keywords: D3DKMTReclaimAllocations, D3DKMTReclaimAllocations callback function [Display Devices], PFND3DKMT_RECLAIMALLOCATIONS, PFND3DKMT_RECLAIMALLOCATIONS callback, d3dkmthk/D3DKMTReclaimAllocations, display.d3dkmtreclaimallocations
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3DKMT_RECLAIMALLOCATIONS
 - d3dkmthk/PFND3DKMT_RECLAIMALLOCATIONS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmthk.h
api_name:
 - PFND3DKMT_RECLAIMALLOCATIONS
---

# PFND3DKMT_RECLAIMALLOCATIONS callback function


## -description

Reclaims video memory allocations.

## -parameters

### -param Arg1

*pData* 

[in, out] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_reclaimallocations">D3DKMT_RECLAIMALLOCATIONS</a> structure that defines memory allocations to reclaim.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The allocations were successfully reclaimed.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display device was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtofferallocations">D3DKMTOfferAllocations</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_reclaimallocations">D3DKMT_RECLAIMALLOCATIONS</a>

