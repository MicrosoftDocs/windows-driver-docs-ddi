---
UID: NS:d3dkmthk._D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP
title: "_D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP"
author: windows-driver-content
description: The D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure describes the parameters to determine the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN.
old-location: display\d3dkmt_checkvidpnexclusiveownership.htm
ms.assetid: 5a7f05a0-11ae-49ed-9015-f2712cc77880
ms.date: 05/10/2018
ms.keywords: D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP, D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure [Display Devices], OpenGL_Structs_23afa7dd-8aaa-402b-9b99-235be17cd26e.xml, _D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP, d3dkmthk/D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP, display.d3dkmt_checkvidpnexclusiveownership
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP is supported beginning with the Windows 7 operating system.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP
---

# _D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure


## -description


The D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure describes the parameters to determine the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN.


## -struct-fields




### -field hAdapter

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the graphics adapter. 


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology to check about. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546779">D3DKMTCheckVidPnExclusiveOwnership</a>
 

 

