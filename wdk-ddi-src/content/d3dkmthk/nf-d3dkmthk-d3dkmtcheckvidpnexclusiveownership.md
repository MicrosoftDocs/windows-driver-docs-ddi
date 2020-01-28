---
UID: NF:d3dkmthk.D3DKMTCheckVidPnExclusiveOwnership
title: D3DKMTCheckVidPnExclusiveOwnership function (d3dkmthk.h)
description: The D3DKMTCheckVidPnExclusiveOwnership function determines the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN.
old-location: display\d3dkmtcheckvidpnexclusiveownership.htm
ms.assetid: 06333989-177c-4c58-b95a-60313c04fe35
ms.date: 05/10/2018
ms.keywords: D3DKMTCheckVidPnExclusiveOwnership, D3DKMTCheckVidPnExclusiveOwnership callback function [Display Devices], OpenGL_Functions_edc90d51-f7e4-4bb5-be24-1a32b9fb4461.xml, PFND3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP, PFND3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP callback, d3dkmthk/D3DKMTCheckVidPnExclusiveOwnership, display.d3dkmtcheckvidpnexclusiveownership
f1_keywords:
 - "d3dkmthk/D3DKMTCheckVidPnExclusiveOwnership"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTCheckVidPnExclusiveOwnership is supported beginning with the Windows 7 operating system.
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
api_name:
- D3DKMTCheckVidPnExclusiveOwnership
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTCheckVidPnExclusiveOwnership function

## -description

The <b>D3DKMTCheckVidPnExclusiveOwnership</b> function determines the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN. 

## -parameters

### -param D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_checkvidpnexclusiveownership">D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP</a> structure that describes the parameters to determine exclusive VidPN ownership. 

## -returns

<b>D3DKMTCheckVidPnExclusiveOwnership</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | Exclusive ownership of the VidPN was successfully determined. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_GRAPHICS_VIDPN_SOURCE_IN_USE** | The video present source that is identified by the VidPnSourceId member of [D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_checkvidpnexclusiveownership) is already owned by a display mode manager (DMM) client and cannot be used until the client releases the video present source. | 
| **STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE** | The video present source that is identified by the VidPnSourceId member of D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP is invalid. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
 
This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_checkvidpnexclusiveownership">D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP</a>
 

 

