---
UID: NF:d3dkmthk.D3DKMTOpenAdapterFromDeviceName
title: D3DKMTOpenAdapterFromDeviceName function (d3dkmthk.h)
description: The D3DKMTOpenAdapterFromDeviceName function maps a device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.
old-location: display\d3dkmtopenadapterfromdevicename.htm
ms.date: 05/10/2018
keywords: ["D3DKMTOpenAdapterFromDeviceName function"]
ms.keywords: D3DKMTOpenAdapterFromDeviceName, D3DKMTOpenAdapterFromDeviceName function [Display Devices], OpenGL_Functions_8298711e-9466-4e00-b77a-0c7a1ee88bed.xml, d3dkmthk/D3DKMTOpenAdapterFromDeviceName, display.d3dkmtopenadapterfromdevicename
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
 - D3DKMTOpenAdapterFromDeviceName
 - d3dkmthk/D3DKMTOpenAdapterFromDeviceName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - API-MS-Win-dx-d3dkmt-l1-1-0.dll
 - API-MS-Win-dx-d3dkmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTOpenAdapterFromDeviceName
---

# D3DKMTOpenAdapterFromDeviceName function


## -description

The <b>D3DKMTOpenAdapterFromDeviceName</b> function maps a device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_openadapterfromdevicename">D3DKMT_OPENADAPTERFROMDEVICENAME</a> structure that describes the parameters that are required to perform the mapping.

## -returns

<b>D3DKMTOpenAdapterFromDeviceName</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The mapping was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect or the Windows Vista display driver model was not used.|

This function might also return other NTSTATUS values.

## -remarks

A graphics adapter corresponds to a video card. A monitor output corresponds to a head on a video card. A system with a single video card contains only one adapter. However, if the video card supports multiple heads, it supports outputting to multiple monitors.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_openadapterfromdevicename">D3DKMT_OPENADAPTERFROMDEVICENAME</a>
