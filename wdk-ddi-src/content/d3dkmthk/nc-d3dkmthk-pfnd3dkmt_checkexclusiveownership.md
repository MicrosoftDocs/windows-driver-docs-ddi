---
UID: NC:d3dkmthk.PFND3DKMT_CHECKEXCLUSIVEOWNERSHIP
title: PFND3DKMT_CHECKEXCLUSIVEOWNERSHIP (d3dkmthk.h)
description: The PFND3DKMT_CHECKEXCLUSIVEOWNERSHIP function checks whether any kernel device object in the operating system is an exclusive owner of any video present sources.
old-location: display\d3dkmtcheckexclusiveownership.htm
ms.date: 03/03/2022
keywords: ["PFND3DKMT_CHECKEXCLUSIVEOWNERSHIP callback function"]
ms.keywords: D3DKMTCheckExclusiveOwnership, D3DKMTCheckExclusiveOwnership callback function [Display Devices], OpenGL_Functions_f5c7a3e5-651c-48f0-b58c-4a6571c10a61.xml, PFND3DKMT_CHECKEXCLUSIVEOWNERSHIP, PFND3DKMT_CHECKEXCLUSIVEOWNERSHIP callback, d3dkmthk/D3DKMTCheckExclusiveOwnership, display.d3dkmtcheckexclusiveownership
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3DKMT_CHECKEXCLUSIVEOWNERSHIP
 - d3dkmthk/PFND3DKMT_CHECKEXCLUSIVEOWNERSHIP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmthk.h
api_name:
 - PFND3DKMT_CHECKEXCLUSIVEOWNERSHIP
---

# PFND3DKMT_CHECKEXCLUSIVEOWNERSHIP callback function

## -description

The **D3DKMTCheckExclusiveOwnership** function checks whether any kernel device object in the operating system has an exclusive level of ownership of any video present sources.

## -parameters

### -param unnamedParam1

## -returns

**D3DKMTCheckExclusiveOwnership** returns a Boolean value that indicates **TRUE** if any kernel device object in the operating system has an exclusive level of ownership of any video present sources and **FALSE** otherwise.

## -remarks

For a description of ownership levels of video present sources, see the [D3DKMTSetVidPnSourceOwnerfunction](nf-d3dkmthk-d3dkmtsetvidpnsourceowner.md) and the [D3DKMT_SETVIDPNSOURCEOWNER](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md) structure. An exclusive level of ownership is represented by the *D3DKMT_VIDPNSOURCEOWNER_EXCLUSIVE* or *D3DKMT_VIDPNSOURCEOWNER_EXCLUSIVEGDI* owner type, which can be specified in one of the elements in the array that the *pType* member of **D3DKMT_SETVIDPNSOURCEOWNER** specifies.

## -see-also

[D3DKMTSetVidPnSourceOwner](nf-d3dkmthk-d3dkmtsetvidpnsourceowner.md)

[D3DKMT_SETVIDPNSOURCEOWNER](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md)
