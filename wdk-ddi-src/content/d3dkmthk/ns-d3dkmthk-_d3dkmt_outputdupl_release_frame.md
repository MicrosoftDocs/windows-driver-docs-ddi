---
UID: NS:d3dkmthk._D3DKMT_OUTPUTDUPL_RELEASE_FRAME
title: _D3DKMT_OUTPUTDUPL_RELEASE_FRAME (d3dkmthk.h)
description: Defines the duplicated desktop image that is to be released in a call to the D3DKMTOutputDuplReleaseFrame function.
old-location: display\d3dkmt_outputdupl_release_frame.htm
ms.assetid: 98d31b6b-c31a-4509-a89f-f09932468313
ms.date: 05/10/2018
keywords: ["_D3DKMT_OUTPUTDUPL_RELEASE_FRAME structure"]
ms.keywords: D3DKMT_OUTPUTDUPL_RELEASE_FRAME, D3DKMT_OUTPUTDUPL_RELEASE_FRAME structure [Display Devices], _D3DKMT_OUTPUTDUPL_RELEASE_FRAME, d3dkmthk/D3DKMT_OUTPUTDUPL_RELEASE_FRAME, display.d3dkmt_outputdupl_release_frame
f1_keywords:
 - "d3dkmthk/D3DKMT_OUTPUTDUPL_RELEASE_FRAME"
 - "D3DKMT_OUTPUTDUPL_RELEASE_FRAME"
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
- D3DKMT_OUTPUTDUPL_RELEASE_FRAME
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_OUTPUTDUPL_RELEASE_FRAME
---

# _D3DKMT_OUTPUTDUPL_RELEASE_FRAME structure


## -description


Defines the duplicated desktop image that is to be released in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtoutputduplreleaseframe">D3DKMTOutputDuplReleaseFrame</a> function.


## -struct-fields




### -field hAdapter

[in] A handle of type <b>D3DKMT_HANDLE</b> that represents a kernel-mode handle to the graphics adapter that contains the duplicated desktop image.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology.


### -field NextKeyMutexIdx

 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtoutputduplreleaseframe">D3DKMTOutputDuplReleaseFrame</a>
 

 

