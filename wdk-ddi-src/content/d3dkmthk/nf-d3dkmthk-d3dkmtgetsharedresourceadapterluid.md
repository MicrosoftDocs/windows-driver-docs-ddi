---
UID: NF:d3dkmthk.D3DKMTGetSharedResourceAdapterLuid
title: D3DKMTGetSharedResourceAdapterLuid function (d3dkmthk.h)
description: Maps a shared resource to a locally unique identifier (LUID) that identifies the graphics adapter that the resource was created on.
old-location: display\d3dkmtgetsharedresourceadapterluid.htm
ms.assetid: 880bf5bd-eadc-480f-a10c-f6d57f670857
ms.date: 05/10/2018
ms.keywords: D3DKMTGetSharedResourceAdapterLuid, D3DKMTGetSharedResourceAdapterLuid function [Display Devices], d3dkmthk/D3DKMTGetSharedResourceAdapterLuid, display.d3dkmtgetsharedresourceadapterluid
ms.topic: function
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- GDI32.dll
- API-MS-Win-dx-d3dkmt-l1-1-0.dll
- API-MS-Win-dx-d3dkmt-l1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTGetSharedResourceAdapterLuid
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTGetSharedResourceAdapterLuid function

## -description

Maps a shared resource to a locally unique identifier (LUID) that identifies the graphics adapter that the resource was created on.

## -parameters

### -param Arg1

*pLuid* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_getsharedresourceadapterluid">D3DKMT_GETSHAREDRESOURCEADAPTERLUID</a> structure that describes a shared resource and the graphics adapter that the resource was created on.


## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The mapping was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_getsharedresourceadapterluid">D3DKMT_GETSHAREDRESOURCEADAPTERLUID</a>
 
