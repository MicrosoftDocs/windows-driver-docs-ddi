---
UID: NF:d3dkmthk.D3DKMTCheckExclusiveOwnership
title: D3DKMTCheckExclusiveOwnership function (d3dkmthk.h)
description: The D3DKMTCheckExclusiveOwnership function checks whether any kernel device object in the operating system has an exclusive level of ownership of any video present sources.
old-location: display\d3dkmtcheckexclusiveownership.htm
ms.assetid: 1695abc2-13ef-4168-b3f5-e9e8be55c5f0
ms.date: 05/10/2018
keywords: ["D3DKMTCheckExclusiveOwnership function"]
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTCheckExclusiveOwnership
 - d3dkmthk/D3DKMTCheckExclusiveOwnership
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTCheckExclusiveOwnership
---

# D3DKMTCheckExclusiveOwnership function


## -description

The <b>D3DKMTCheckExclusiveOwnership</b> function checks whether any kernel device object in the operating system has an exclusive level of ownership of any video present sources.

## -parameters

## -returns

<b>D3DKMTCheckExclusiveOwnership</b> returns a Boolean value that indicates <b>TRUE</b> if any kernel device object in the operating system has an exclusive level of ownership of any video present sources and <b>FALSE</b> otherwise.

## -remarks

For a description of ownership levels of video present sources, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetvidpnsourceowner">D3DKMTSetVidPnSourceOwner</a> function and the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setvidpnsourceowner">D3DKMT_SETVIDPNSOURCEOWNER</a> structure. An exclusive level of ownership is represented by the D3DKMT_VIDPNSOURCEOWNER_EXCLUSIVE or D3DKMT_VIDPNSOURCEOWNER_EXCLUSIVEGDI owner type, which can be specified in one of the elements in the array that the <b>pType</b> member of D3DKMT_SETVIDPNSOURCEOWNER specifies.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetvidpnsourceowner">D3DKMTSetVidPnSourceOwner</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setvidpnsourceowner">D3DKMT_SETVIDPNSOURCEOWNER</a>

