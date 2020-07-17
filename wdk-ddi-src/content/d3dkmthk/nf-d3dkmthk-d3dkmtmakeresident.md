---
UID: NF:d3dkmthk.D3DKMTMakeResident
title: D3DKMTMakeResident function (d3dkmthk.h)
description: D3DKMTMakeResident is used to add a resource to the device residency list and increment the residency reference count on this allocation.
old-location: display\d3dkmtmakeresident.htm
ms.assetid: 5F4E17CB-3B8B-4BBA-A819-B8E28183F1CB
ms.date: 05/10/2018
keywords: ["D3DKMTMakeResident function"]
ms.keywords: D3DKMTMakeResident, D3DKMTMakeResident function [Display Devices], d3dkmthk/D3DKMTMakeResident, display.d3dkmtmakeresident
f1_keywords:
 - "d3dkmthk/D3DKMTMakeResident"
 - "D3DKMTMakeResident"
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
- D3DKMTMakeResident
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTMakeResident function


## -description

<b>D3DKMTMakeResident</b> is used to add a resource to the device residency list and increment the residency reference count on this allocation.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-d3dddi_makeresident">D3DDDI_MAKERESIDENT</a> structure that describes the operation.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The operation was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-d3dddi_makeresident">D3DDDI_MAKERESIDENT</a>
 

 

