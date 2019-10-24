---
UID: NF:d3dkmthk.D3DKMTQueryResourceInfo
title: D3DKMTQueryResourceInfo function (d3dkmthk.h)
description: The D3DKMTQueryResourceInfo function retrieves information about a shared resource.
old-location: display\d3dkmtqueryresourceinfo.htm
ms.assetid: d195634e-d626-43c9-8212-f32b95c1f526
ms.date: 05/10/2018
ms.keywords: D3DKMTQueryResourceInfo, D3DKMTQueryResourceInfo function [Display Devices], OpenGL_Functions_77dad2ba-a352-4b1a-b2be-53c41589bf90.xml, d3dkmthk/D3DKMTQueryResourceInfo, display.d3dkmtqueryresourceinfo
ms.topic: function
f1_keywords:
 - "d3dkmthk/D3DKMTQueryResourceInfo"
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
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTQueryResourceInfo function

## -description

The <b>D3DKMTQueryResourceInfo</b> function retrieves information about a shared resource.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryresourceinfo">D3DKMT_QUERYRESOURCEINFO</a> structure that contains parameters for retrieving information about a shared resource.

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

The OpenGL ICD typically calls <b>D3DKMTQueryResourceInfo</b> to obtain information about the resource and then uses this information to allocate the appropriate buffers for a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenresource">D3DKMTOpenResource</a>.

For an example of how an OpenGL ICD can use <b>D3DKMTQueryResourceInfo</b> to retrieve information about a shared resource, see the code example in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenresource">D3DKMTOpenResource</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenresource">D3DKMTOpenResource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryresourceinfo">D3DKMT_QUERYRESOURCEINFO</a>
 

 

