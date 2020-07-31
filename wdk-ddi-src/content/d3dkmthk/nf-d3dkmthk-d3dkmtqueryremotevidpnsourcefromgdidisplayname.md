---
UID: NF:d3dkmthk.D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName
title: D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName function (d3dkmthk.h)
description: Maps a GDI display name to a remote video present network (VidPN) source ID that is needed for a call to the D3DKMTOutputDuplPresent function.
old-location: display\d3dkmtqueryremotevidpnsourcefromgdidisplayname.htm
ms.assetid: 3606d5f4-760f-4ba1-84ea-218b6c2a2e20
ms.date: 05/10/2018
keywords: ["D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName function"]
ms.keywords: D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName, D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName callback function [Display Devices], PFND3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME, PFND3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME callback, d3dkmthk/D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName, display.d3dkmtqueryremotevidpnsourcefromgdidisplayname
f1_keywords:
 - "d3dkmthk/D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName"
 - "D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName"
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
- Gdi32.dll
api_name:
- D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName function

## -description

Maps a GDI display name to a remote video present network (VidPN) source ID that is needed for a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtoutputduplpresent">D3DKMTOutputDuplPresent</a> function.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryremotevidpnsourcefromgdidisplayname">D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME</a> structure that describes information that is required to perform the mapping.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The mapping was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other NTSTATUS values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtoutputduplpresent">D3DKMTOutputDuplPresent</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryremotevidpnsourcefromgdidisplayname">D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME</a>
