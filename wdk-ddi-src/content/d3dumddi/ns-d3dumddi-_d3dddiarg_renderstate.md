---
UID: NS:d3dumddi._D3DDDIARG_RENDERSTATE
title: "_D3DDDIARG_RENDERSTATE"
author: windows-driver-content
description: The D3DDDIARG_RENDERSTATE structure describes how to update a specific render state.
old-location: display\d3dddiarg_renderstate.htm
old-project: display
ms.assetid: 177a2578-2bd4-4a11-a3fd-fec226a64c22
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDIARG_RENDERSTATE, D3DDDIARG_RENDERSTATE structure [Display Devices], UMDisplayDriver_param_Structs_4d558ee2-a265-4973-90d4-917170d01ef3.xml, _D3DDDIARG_RENDERSTATE, d3dumddi/D3DDDIARG_RENDERSTATE, display.d3dddiarg_renderstate
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
-	D3DDDIARG_RENDERSTATE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_RENDERSTATE
---

# _D3DDDIARG_RENDERSTATE structure


## -description


The D3DDDIARG_RENDERSTATE structure describes how to update a specific render state. 


## -struct-fields




### -field State

[in] A D3DDDIRENDERSTATETYPE-typed value that indicates the render state to be updated. For a definition of each value, see the corresponding value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549036">D3DRENDERSTATETYPE</a> enumeration type in the DirectX documentation.


### -field Value

[in] The value to which the driver should update the render state that is identified by the <b>State</b> member. For more information about values that can be updated for each render state, see the definition of the corresponding render state in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549036">D3DRENDERSTATETYPE</a> enumeration type in the DirectX documentation.


## -see-also




<a href="https://msdn.microsoft.com/22fb67f7-cc28-4f10-950d-1379769ddf89">SetRenderState</a>
 

 

