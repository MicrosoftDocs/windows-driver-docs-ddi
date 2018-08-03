---
UID: NS:d3dumddi._D3DDDICB_CREATEOVERLAY
title: "_D3DDDICB_CREATEOVERLAY"
author: windows-driver-content
description: The D3DDDICB_CREATEOVERLAY structure describes overlay hardware.
old-location: display\d3dddicb_createoverlay.htm
tech.root: display
ms.assetid: 52f95379-7bfd-4606-9199-ea253ccd6f35
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDICB_CREATEOVERLAY, D3DDDICB_CREATEOVERLAY structure [Display Devices], D3D_param_Structs_d6883734-5c4a-480f-bb54-12df15297daa.xml, _D3DDDICB_CREATEOVERLAY, d3dumddi/D3DDDICB_CREATEOVERLAY, display.d3dddicb_createoverlay
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDICB_CREATEOVERLAY
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_CREATEOVERLAY
---

# _D3DDDICB_CREATEOVERLAY structure


## -description


The D3DDDICB_CREATEOVERLAY structure describes overlay hardware.


## -struct-fields




### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology to overlay on (that is, the identifier of the primary surface to overlay on). 


### -field OverlayInfo

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544577">D3DDDI_KERNELOVERLAYINFO</a> structure that describes information about the kernel-mode overlay object.


### -field hKernelOverlay

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the kernel-mode overlay object. This overlay object represents the overlay hardware in subsequent calls by the user-mode display driver to the Microsoft Direct3D runtime.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544577">D3DDDI_KERNELOVERLAYINFO</a>



<a href="https://msdn.microsoft.com/fbd5b3af-0963-4e41-8be3-41e3e1ecf8bc">pfnCreateOverlayCb</a>
 

 

