---
UID: NF:d3dkmthk.D3DKMTOpenAdapterFromLuid
title: D3DKMTOpenAdapterFromLuid function (d3dkmthk.h)
description: Maps a locally unique identifier (LUID) to a graphics adapter handle.
old-location: display\d3dkmtopenadapterfromluid.htm
ms.assetid: 1007c8ba-c503-4522-aef8-23b89bec3d62
ms.date: 05/10/2018
ms.keywords: D3DKMTOpenAdapterFromLuid, D3DKMTOpenAdapterFromLuid function [Display Devices], d3dkmthk/D3DKMTOpenAdapterFromLuid, display.d3dkmtopenadapterfromluid
ms.topic: function
f1_keywords:
 - "d3dkmthk/D3DKMTOpenAdapterFromLuid"
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
- API-MS-Win-DX-D3DKMT-L1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTOpenAdapterFromLuid
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTOpenAdapterFromLuid function

## -description

Maps a locally unique identifier (LUID) to a graphics adapter handle.

## -parameters

### -param D3DKMT_OPENADAPTERFROMLUID

*pAdapter* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_openadapterfromluid">D3DKMT_OPENADAPTERFROMLUID</a> structure that describes information that is required to perform the mapping.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The mapping was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other NTSTATUS values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_openadapterfromluid">D3DKMT_OPENADAPTERFROMLUID</a>
 

 

