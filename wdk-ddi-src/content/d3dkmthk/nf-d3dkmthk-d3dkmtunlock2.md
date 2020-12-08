---
UID: NF:d3dkmthk.D3DKMTUnlock2
title: D3DKMTUnlock2 function (d3dkmthk.h)
description: The D3DKMTUnlock2 function unlocks a list of allocations.
old-location: display\d3dkmtunlock2.htm
ms.date: 05/10/2018
keywords: ["D3DKMTUnlock2 function"]
ms.keywords: D3DKMTUnlock2, D3DKMTUnlock2 function [Display Devices], d3dkmthk/D3DKMTUnlock2, display.d3dkmtunlock2
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTUnlock2
 - d3dkmthk/D3DKMTUnlock2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - API-MS-Win-DX-D3DKMT-L1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTUnlock2
---

# D3DKMTUnlock2 function


## -description

The <b>D3DKMTUnlock2</b> function unlocks a list of allocations.

## -parameters

### -param D3DKMT_UNLOCK2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_unlock2">D3DKMT_UNLOCK2</a> structure that describes a list of allocations to unlock.

## -returns

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The allocations were successfully unlocked.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_unlock2">D3DKMT_UNLOCK2</a>
