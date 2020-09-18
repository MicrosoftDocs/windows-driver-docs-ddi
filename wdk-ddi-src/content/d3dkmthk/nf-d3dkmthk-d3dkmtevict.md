---
UID: NF:d3dkmthk.D3DKMTEvict
title: D3DKMTEvict function (d3dkmthk.h)
description: D3DKMTEvict is used to decrement the allocation residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.
old-location: display\d3dkmtevict.htm
ms.assetid: 010F7CB0-F930-47FF-91DF-D95B21FC76A0
ms.date: 05/10/2018
keywords: ["D3DKMTEvict function"]
ms.keywords: D3DKMTEvict, D3DKMTEvict function [Display Devices], d3dkmthk/D3DKMTEvict, display.d3dkmtevict
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
 - D3DKMTEvict
 - d3dkmthk/D3DKMTEvict
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
 - D3DKMTEvict
---

# D3DKMTEvict function


## -description

<b>D3DKMTEvict</b> is used to decrement the allocation residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_evict">D3DKMT_EVICT</a> structure that describes the operation.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The operation was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -remarks

Once the eviction request is queued, it is illegal to access the underlying allocation as the allocation may be evicted at anytime from there on at the operating system discretion.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_evict">D3DKMT_EVICT</a>

