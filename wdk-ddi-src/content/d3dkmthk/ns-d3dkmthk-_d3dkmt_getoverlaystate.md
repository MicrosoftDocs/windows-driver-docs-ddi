---
UID: NS:d3dkmthk._D3DKMT_GETOVERLAYSTATE
title: _D3DKMT_GETOVERLAYSTATE (d3dkmthk.h)
description: The D3DKMT_GETOVERLAYSTATE structure describes parameters that the D3DKMTGetOverlayState function uses to retrieve status about an overlay.
old-location: display\d3dkmt_getoverlaystate.htm
ms.assetid: fe3443e7-0dc9-4c91-88ab-b05bac19516d
ms.date: 05/10/2018
ms.keywords: D3DKMT_GETOVERLAYSTATE, D3DKMT_GETOVERLAYSTATE structure [Display Devices], OpenGL_Structs_c9bee52b-d6ba-45ee-9af6-b795685715bb.xml, _D3DKMT_GETOVERLAYSTATE, d3dkmthk/D3DKMT_GETOVERLAYSTATE, display.d3dkmt_getoverlaystate
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_GETOVERLAYSTATE"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_GETOVERLAYSTATE is supported beginning with the Windows 7 operating system.
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
- D3DKMT_GETOVERLAYSTATE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_GETOVERLAYSTATE
---

# _D3DKMT_GETOVERLAYSTATE structure


## -description


The D3DKMT_GETOVERLAYSTATE structure describes parameters that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtgetoverlaystate">D3DKMTGetOverlayState</a> function uses to retrieve status about an overlay. 


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the device that the overlay is associated with.


### -field hOverlay

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the create-overlay function and that identifies the kernel-mode overlay object to retrieve status about. 


### -field OverlayEnabled

[out] A Boolean variable that receives <b>TRUE</b> if the overlay is enabled and <b>FALSE</b> if the overlay is disabled. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtgetoverlaystate">D3DKMTGetOverlayState</a>
 

 

