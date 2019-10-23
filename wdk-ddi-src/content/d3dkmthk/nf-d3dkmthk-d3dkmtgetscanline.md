---
UID: NF:d3dkmthk.D3DKMTGetScanLine
title: D3DKMTGetScanLine function (d3dkmthk.h)
description: The D3DKMTGetScanLine function determines whether the given video present source of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.
old-location: display\d3dkmtgetscanline.htm
ms.assetid: 052507ec-4a26-4bb6-8876-c03a9c81f412
ms.date: 05/10/2018
ms.keywords: D3DKMTGetScanLine, D3DKMTGetScanLine function [Display Devices], OpenGL_Functions_3a2d269d-0867-42fb-9268-86c560531de4.xml, d3dkmthk/D3DKMTGetScanLine, display.d3dkmtgetscanline
ms.topic: function
f1_keywords:
 - "d3dkmthk/D3DKMTGetScanLine"
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
- D3DKMTGetScanLine
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTGetScanLine function

## -description

The <b>D3DKMTGetScanLine</b> function determines whether the given video present source of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getscanline">D3DKMT_GETSCANLINE</a> structure that contains the vertical blanking status of a video present source.

## -returns

<b>D3DKMTGetScanLine</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The vertical blanking status and scan line were successfully retrieved.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getscanline">D3DKMT_GETSCANLINE</a>
 

 

