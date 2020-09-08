---
UID: NC:d3dkmthk.PFND3DKMT_SETVIDPNSOURCEOWNER1
title: PFND3DKMT_SETVIDPNSOURCEOWNER1 (d3dkmthk.h)
description: Sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN, and lets output duplication options be specified. Supported starting with Windows 8.
old-location: display\d3dkmtsetvidpnsourceowner1.htm
ms.assetid: ccee5459-f156-41c3-b9a1-8bd7d16c8d19
ms.date: 05/10/2018
keywords: ["PFND3DKMT_SETVIDPNSOURCEOWNER1 callback function"]
ms.keywords: D3DKMTSetVidPnSourceOwner1, D3DKMTSetVidPnSourceOwner1 callback function [Display Devices], PFND3DKMT_SETVIDPNSOURCEOWNER1, PFND3DKMT_SETVIDPNSOURCEOWNER1 callback, d3dkmthk/D3DKMTSetVidPnSourceOwner1, display.d3dkmtsetvidpnsourceowner1
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3DKMT_SETVIDPNSOURCEOWNER1
 - d3dkmthk/PFND3DKMT_SETVIDPNSOURCEOWNER1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMTSetVidPnSourceOwner1
---

# PFND3DKMT_SETVIDPNSOURCEOWNER1 callback function


## -description

Sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN, and  lets output duplication options be specified. Supported starting with Windows 8.

## -parameters

### -param Arg1

*pSetVidPnSourceOwner1* 

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setvidpnsourceowner1">D3DKMT_SETVIDPNSOURCEOWNER1</a> structure that describes the parameters for setting or releasing the video present source.

## -returns

Returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The video present source was successfully set or released. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_GRAPHICS_VIDPN_SOURCE_IN_USE** | The video present source that is specified by an element in the array that the pVidPnSourceId member of [D3DKMT_SETVIDPNSOURCEOWNER](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setvidpnsourceowner) specifies is already owned by a display mode manager (DMM) client and cannot be used until the client releases the video present source. | 
| **STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE** | The video present source that is specified by an element in the array that the pVidPnSourceId member of [D3DKMT_SETVIDPNSOURCEOWNER](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setvidpnsourceowner) specifies is invalid. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 

This function might also return other NTSTATUS values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setvidpnsourceowner1">D3DKMT_SETVIDPNSOURCEOWNER1</a>

