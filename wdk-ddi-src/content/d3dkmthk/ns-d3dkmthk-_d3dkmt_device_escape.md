---
UID: NS:d3dkmthk._D3DKMT_DEVICE_ESCAPE
title: _D3DKMT_DEVICE_ESCAPE (d3dkmthk.h)
description: Do not use the D3DKMT_DEVICE_ESCAPE structure or D3DKMT_DEVICEESCAPE_TYPE enumeration. They are for testing purposes only. The D3DKMT_DEVICE_ESCAPE structure describes how to control the display device in a call to the D3DKMTEscape function.
old-location: display\d3dkmt_device_escape.htm
ms.assetid: 274bdd80-e898-42c7-8adc-8eae4e895b5f
ms.date: 05/10/2018
ms.keywords: D3DKMT_DEVICE_ESCAPE, D3DKMT_DEVICE_ESCAPE structure [Display Devices], OpenGL_Structs_38febe04-ae75-475a-ab69-81995acb567b.xml, _D3DKMT_DEVICE_ESCAPE, d3dkmthk/D3DKMT_DEVICE_ESCAPE, display.d3dkmt_device_escape
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_DEVICE_ESCAPE"
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
- D3DKMT_DEVICE_ESCAPE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DEVICE_ESCAPE
---

# _D3DKMT_DEVICE_ESCAPE structure


## -description



   Do not use the D3DKMT_DEVICE_ESCAPE structure or D3DKMT_DEVICEESCAPE_TYPE enumeration. They are for testing purposes only.
   

The D3DKMT_DEVICE_ESCAPE structure describes how to control the display device in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtescape">D3DKMTEscape</a> function.


## -struct-fields




### -field Type


### -field VidPnFromAllocation


### -field VidPnFromAllocation.hPrimaryAllocation

[in] The primary allocation handle.


### -field VidPnFromAllocation.VidPnSourceId

[out] The VidPN source ID of the primary allocation.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtescape">D3DKMTEscape</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_escape">D3DKMT_ESCAPE</a>
 

 

