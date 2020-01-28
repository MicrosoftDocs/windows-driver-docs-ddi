---
UID: NS:d3dumddi._D3DDDIARG_SETPRIORITY
title: _D3DDDIARG_SETPRIORITY (d3dumddi.h)
description: The D3DDDIARG_SETPRIORITY structure describes the priority level to set for a managed texture.
old-location: display\d3dddiarg_setpriority.htm
tech.root: display
ms.assetid: d3dd52de-6d28-4d71-9b64-ba79e17bd9ee
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_SETPRIORITY, D3DDDIARG_SETPRIORITY structure [Display Devices], UMDisplayDriver_param_Structs_e416cff1-5cad-4488-a3e2-ea0b42a7cd81.xml, _D3DDDIARG_SETPRIORITY, d3dumddi/D3DDDIARG_SETPRIORITY, display.d3dddiarg_setpriority
f1_keywords:
 - "d3dumddi/D3DDDIARG_SETPRIORITY"
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
- D3DDDIARG_SETPRIORITY
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_SETPRIORITY
---

# _D3DDDIARG_SETPRIORITY structure


## -description


The D3DDDIARG_SETPRIORITY structure describes the priority level to set for a managed texture. 


## -struct-fields




### -field hResource

A handle to the resource that contains the texture.


### -field Priority

The priority level to set for the texture that is contained in the <b>hResource</b> resource. A texture's priority value can be set anywhere in the range from 0 through 0xFFFFFFFF.


## -remarks



The driver receives only priority notifications for driver-managed textures.

The priority level at which a texture is set determines its eviction order from memory. A texture that is assigned a low priority is evicted before a texture with a high priority. If two textures have the same priority, the texture that was used more recently is kept in memory; the other texture is evicted. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setpriority">SetPriority</a>
 

 

