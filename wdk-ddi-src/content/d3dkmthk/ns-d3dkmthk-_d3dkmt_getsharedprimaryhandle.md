---
UID: NS:d3dkmthk._D3DKMT_GETSHAREDPRIMARYHANDLE
title: _D3DKMT_GETSHAREDPRIMARYHANDLE (d3dkmthk.h)
description: The D3DKMT_GETSHAREDPRIMARYHANDLE structure describes the parameters that are required to retrieve the global shared handle for the primary surface.
old-location: display\d3dkmt_getsharedprimaryhandle.htm
ms.assetid: 59c45a0e-54c3-4301-8e65-409d6c728325
ms.date: 05/10/2018
ms.keywords: D3DKMT_GETSHAREDPRIMARYHANDLE, D3DKMT_GETSHAREDPRIMARYHANDLE structure [Display Devices], OpenGL_Structs_322563d8-5546-4b10-bd74-101f3ffb633a.xml, _D3DKMT_GETSHAREDPRIMARYHANDLE, d3dkmthk/D3DKMT_GETSHAREDPRIMARYHANDLE, display.d3dkmt_getsharedprimaryhandle
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_GETSHAREDPRIMARYHANDLE"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_GETSHAREDPRIMARYHANDLE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_GETSHAREDPRIMARYHANDLE
---

# _D3DKMT_GETSHAREDPRIMARYHANDLE structure


## -description


The D3DKMT_GETSHAREDPRIMARYHANDLE structure describes the parameters that are required to retrieve the global shared handle for the primary surface.


## -struct-fields




### -field hAdapter

[in] A handle to the graphics adapter that the primary surface is associated with.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that displays the primary surface.


### -field hSharedPrimary

[out] A handle to the global shared primary surface if a shared handle currently exists. The shared handle is returned from the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtgetsharedprimaryhandle">D3DKMTGetSharedPrimaryHandle</a> function.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtgetsharedprimaryhandle">D3DKMTGetSharedPrimaryHandle</a>
 

 

