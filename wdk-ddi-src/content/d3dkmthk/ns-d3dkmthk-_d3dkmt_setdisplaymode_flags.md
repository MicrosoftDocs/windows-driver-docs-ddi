---
UID: NS:d3dkmthk._D3DKMT_SETDISPLAYMODE_FLAGS
title: _D3DKMT_SETDISPLAYMODE_FLAGS (d3dkmthk.h)
description: The D3DKMT_SETDISPLAYMODE_FLAGS structure identifies attributes for setting the display mode.
old-location: display\d3dkmt_setdisplaymode_flags.htm
ms.assetid: 245586cb-d277-4cef-aeb9-b576a4ae6d43
ms.date: 05/10/2018
keywords: ["_D3DKMT_SETDISPLAYMODE_FLAGS structure"]
ms.keywords: D3DKMT_SETDISPLAYMODE_FLAGS, D3DKMT_SETDISPLAYMODE_FLAGS structure [Display Devices], OpenGL_Structs_28412793-06ae-4e0d-9461-8e7cbcea8779.xml, _D3DKMT_SETDISPLAYMODE_FLAGS, d3dkmthk/D3DKMT_SETDISPLAYMODE_FLAGS, display.d3dkmt_setdisplaymode_flags
f1_keywords:
 - "d3dkmthk/D3DKMT_SETDISPLAYMODE_FLAGS"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_SETDISPLAYMODE_FLAGS is supported beginning with the Windows 7 operating system.
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
- D3DKMT_SETDISPLAYMODE_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SETDISPLAYMODE_FLAGS
---

# _D3DKMT_SETDISPLAYMODE_FLAGS structure


## -description


The D3DKMT_SETDISPLAYMODE_FLAGS structure identifies attributes for setting the display mode.


## -struct-fields




### -field PreserveVidPn

[in] A Boolean value that specifies whether the video present network (VidPN) for a monitor is preserved. 


### -field Reserved

[in] This member is reserved and should be set to zero. 


## -remarks



To set attributes of the display mode, you specify bitfields of the D3DKMT_SETDISPLAYMODE_FLAGS structure in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setdisplaymode">D3DKMT_SETDISPLAYMODE</a> structure. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setdisplaymode">D3DKMT_SETDISPLAYMODE</a>
 

 

