---
UID: NS:d3dkmddi._DXGKARG_SETPOINTERPOSITION
title: _DXGKARG_SETPOINTERPOSITION (d3dkmddi.h)
description: The DXGKARG_SETPOINTERPOSITION structure describes where and how to display the mouse pointer.
old-location: display\dxgkarg_setpointerposition.htm
ms.assetid: a5670b3e-a96b-439c-ac1a-644611110700
ms.date: 05/10/2018
ms.keywords: DXGKARG_SETPOINTERPOSITION, DXGKARG_SETPOINTERPOSITION structure [Display Devices], DmStructs_2a671f7f-7750-4edb-bf07-7e823ddd309f.xml, _DXGKARG_SETPOINTERPOSITION, d3dkmddi/DXGKARG_SETPOINTERPOSITION, display.dxgkarg_setpointerposition
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGKARG_SETPOINTERPOSITION"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
- d3dkmddi.h
api_name:
- DXGKARG_SETPOINTERPOSITION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_SETPOINTERPOSITION
---

# _DXGKARG_SETPOINTERPOSITION structure


## -description


The DXGKARG_SETPOINTERPOSITION structure describes where and how to display the mouse pointer. 


## -struct-fields




### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the mouse pointer is located on. 


### -field X

[in] The column, in pixels, that the mouse pointer is located on from the top left.


### -field Y

[in] The row, in pixels, that the mouse pointer is located on from the top left.


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_setpointerpositionflags">DXGK_SETPOINTERPOSITIONFLAGS</a> structure that identifies, in bit-field flags, information about the mouse pointer.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_setpointerpositionflags">DXGK_SETPOINTERPOSITIONFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_setpointerposition">DxgkDdiSetPointerPosition</a>
 

 

