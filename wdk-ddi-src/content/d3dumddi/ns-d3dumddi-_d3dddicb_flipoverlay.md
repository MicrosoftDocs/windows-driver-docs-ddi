---
UID: NS:d3dumddi._D3DDDICB_FLIPOVERLAY
title: _D3DDDICB_FLIPOVERLAY (d3dumddi.h)
description: The D3DDDICB_FLIPOVERLAY structure describes a new allocation to display for the overlay.
old-location: display\d3dddicb_flipoverlay.htm
tech.root: display
ms.assetid: 709583a5-5367-4187-a560-29b2c8eedbf4
ms.date: 05/10/2018
ms.keywords: D3DDDICB_FLIPOVERLAY, D3DDDICB_FLIPOVERLAY structure [Display Devices], D3D_param_Structs_cb3914df-9c6b-43f0-a8fa-a2f06f5b2abd.xml, _D3DDDICB_FLIPOVERLAY, d3dumddi/D3DDDICB_FLIPOVERLAY, display.d3dddicb_flipoverlay
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- d3dumddi.h
api_name:
- D3DDDICB_FLIPOVERLAY
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_FLIPOVERLAY
---

# _D3DDDICB_FLIPOVERLAY structure


## -description


The D3DDDICB_FLIPOVERLAY structure describes a new allocation to display for the overlay. 


## -struct-fields




### -field hKernelOverlay

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createoverlaycb">pfnCreateOverlayCb</a> function and that identifies the kernel-mode overlay object to be flipped.


### -field hSource

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the source allocation to be displayed.


### -field pPrivateDriverData

[in] A pointer to a block of private data, which is passed from the user-mode display driver to the display miniport driver. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that is pointed to by <b>pPrivateDriverData</b>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createoverlaycb">pfnCreateOverlayCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_flipoverlaycb">pfnFlipOverlayCb</a>
 

 

