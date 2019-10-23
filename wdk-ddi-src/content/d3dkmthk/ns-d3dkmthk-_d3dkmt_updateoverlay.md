---
UID: NS:d3dkmthk._D3DKMT_UPDATEOVERLAY
title: _D3DKMT_UPDATEOVERLAY (d3dkmthk.h)
description: The D3DKMT_UPDATEOVERLAY structure describes parameters for modifying an overlay.
old-location: display\d3dkmt_updateoverlay.htm
ms.assetid: 4e7d4d09-067b-4658-ab2a-319dc9e6d8db
ms.date: 05/10/2018
ms.keywords: D3DKMT_UPDATEOVERLAY, D3DKMT_UPDATEOVERLAY structure [Display Devices], OpenGL_Structs_763acbbf-27ad-4d91-903f-7200b7d7e0cf.xml, _D3DKMT_UPDATEOVERLAY, d3dkmthk/D3DKMT_UPDATEOVERLAY, display.d3dkmt_updateoverlay
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_UPDATEOVERLAY"
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
- D3DKMT_UPDATEOVERLAY
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_UPDATEOVERLAY
---

# _D3DKMT_UPDATEOVERLAY structure


## -description


The D3DKMT_UPDATEOVERLAY structure describes parameters for modifying an overlay.


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the device that the overlay is associated with.


### -field hOverlay

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the create-overlay function and that identifies the kernel-mode overlay object to modify. 


### -field OverlayInfo

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_kerneloverlayinfo">D3DDDI_KERNELOVERLAYINFO</a> structure that describes modification information for the kernel-mode overlay object. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_kerneloverlayinfo">D3DDDI_KERNELOVERLAYINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtupdateoverlay">D3DKMTUpdateOverlay</a>
 

 

