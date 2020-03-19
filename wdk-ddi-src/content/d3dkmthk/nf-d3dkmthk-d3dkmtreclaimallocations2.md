---
UID: NF:d3dkmthk.D3DKMTReclaimAllocations2
title: D3DKMTReclaimAllocations2 function (d3dkmthk.h)
description: D3DKMTReclaimAllocations2 reclaims video memory allocations.
old-location: display\d3dkmtreclaimallocations2.htm
ms.assetid: 0BC49546-ECDE-447D-8F7E-4235D96D293B
ms.date: 05/10/2018
keywords: ["D3DKMTReclaimAllocations2 function"]
ms.keywords: D3DKMTReclaimAllocations2, D3DKMTReclaimAllocations2 function [Display Devices], d3dkmthk/D3DKMTReclaimAllocations2, display.d3dkmtreclaimallocations2
f1_keywords:
 - "d3dkmthk/D3DKMTReclaimAllocations2"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- API-MS-Win-DX-D3DKMT-L1-1-1.dll
- GDI32.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTReclaimAllocations2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTReclaimAllocations2 function

## -description

<b>D3DKMTReclaimAllocations2</b> reclaims video memory allocations.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_reclaimallocations2">D3DKMT_RECLAIMALLOCATIONS2</a> structure that defines memory allocations to reclaim.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The allocations were successfully reclaimed.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display device was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_reclaimallocations2">D3DKMT_RECLAIMALLOCATIONS2</a>
