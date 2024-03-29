---
UID: NF:d3dkmthk.D3DKMTQueryResourceInfo
title: D3DKMTQueryResourceInfo function (d3dkmthk.h)
description: The D3DKMTQueryResourceInfo function retrieves information about a shared resource.
old-location: display\d3dkmtqueryresourceinfo.htm
ms.date: 05/10/2018
keywords: ["D3DKMTQueryResourceInfo function"]
ms.keywords: D3DKMTQueryResourceInfo, D3DKMTQueryResourceInfo function [Display Devices], OpenGL_Functions_77dad2ba-a352-4b1a-b2be-53c41589bf90.xml, d3dkmthk/D3DKMTQueryResourceInfo, display.d3dkmtqueryresourceinfo
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
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
 - D3DKMTQueryResourceInfo
 - d3dkmthk/D3DKMTQueryResourceInfo
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
 - D3DKMTQueryResourceInfo
---

# D3DKMTQueryResourceInfo function


## -description

The <b>D3DKMTQueryResourceInfo</b> function retrieves information about a shared resource.

## -parameters

### -param unnamedParam1

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryresourceinfo">D3DKMT_QUERYRESOURCEINFO</a> structure that contains parameters for retrieving information about a shared resource.

## -returns

<b>D3DKMTQueryResourceInfo</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|Information about a shared resource was successfully retrieved.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display device was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
|STATUS_INTEGER_OVERFLOW|The size of all of the private driver data was too big to return to the OpenGL ICD.|

This function might also return other NTSTATUS values.

## -remarks

The OpenGL ICD typically calls <b>D3DKMTQueryResourceInfo</b> to obtain information about the resource and then uses this information to allocate the appropriate buffers for a call to <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenresource">D3DKMTOpenResource</a>.

For an example of how an OpenGL ICD can use <b>D3DKMTQueryResourceInfo</b> to retrieve information about a shared resource, see the code example in <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenresource">D3DKMTOpenResource</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenresource">D3DKMTOpenResource</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryresourceinfo">D3DKMT_QUERYRESOURCEINFO</a>
