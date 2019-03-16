---
UID: NS:d3dkmthk._D3DKMT_VIDPNSOURCEOWNER_FLAGS
title: _D3DKMT_VIDPNSOURCEOWNER_FLAGS (d3dkmthk.h)
description: Specifies output duplication options for use with the D3DKMTSetVidPnSourceOwner1 function.
old-location: display\d3dkmt_vidpnsourceowner_flags.htm
ms.assetid: acc4e9d9-235f-4605-ae51-5056108843dc
ms.date: 05/10/2018
ms.keywords: D3DKMT_VIDPNSOURCEOWNER_FLAGS, D3DKMT_VIDPNSOURCEOWNER_FLAGS structure [Display Devices], _D3DKMT_VIDPNSOURCEOWNER_FLAGS, d3dkmthk/D3DKMT_VIDPNSOURCEOWNER_FLAGS, display.d3dkmt_vidpnsourceowner_flags
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmthk.h
api_name:
- D3DKMT_VIDPNSOURCEOWNER_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_VIDPNSOURCEOWNER_FLAGS
---

# _D3DKMT_VIDPNSOURCEOWNER_FLAGS structure


## -description


Specifies output duplication options for use with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439459">D3DKMTSetVidPnSourceOwner1</a> function.


## -struct-fields




### -field AllowOutputDuplication

If a value of one, the video present network (VidPN) explicitly allows output duplication. Otherwise output duplication is not allowed.


### -field DisableDWMVirtualMode

 


### -field UseNtHandles

 


### -field Reserved

Reserved for internal use.


### -field Value

Specifies the number of output duplication paths on the VidPN.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439459">D3DKMTSetVidPnSourceOwner1</a>
 

 

