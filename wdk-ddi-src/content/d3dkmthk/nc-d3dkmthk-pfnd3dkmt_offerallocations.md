---
UID: NC:d3dkmthk.PFND3DKMT_OFFERALLOCATIONS
title: PFND3DKMT_OFFERALLOCATIONS (d3dkmthk.h)
description: Offers video memory allocations for reuse.
old-location: display\d3dkmtofferallocations.htm
ms.assetid: 3cc84381-fa1e-4c6c-bb5b-459a93676cfd
ms.date: 05/10/2018
ms.keywords: D3DKMTOfferAllocations, D3DKMTOfferAllocations callback function [Display Devices], PFND3DKMT_OFFERALLOCATIONS, PFND3DKMT_OFFERALLOCATIONS callback, d3dkmthk/D3DKMTOfferAllocations, display.d3dkmtofferallocations
ms.topic: callback
f1_keywords:
 - "d3dkmthk/D3DKMTOfferAllocations"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3dkmthk.h
api_name:
- D3DKMTOfferAllocations
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DKMT_OFFERALLOCATIONS callback function


## -description

Offers video memory allocations for reuse.

## -parameters

### -param *

*pData* 

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_offerallocations">D3DKMT_OFFERALLOCATIONS</a> structure that defines memory allocations that the driver offers for reuse.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The allocations were successfully offered.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display device was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtreclaimallocations">D3DKMTReclaimAllocations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_offerallocations">D3DKMT_OFFERALLOCATIONS</a>
 

 

