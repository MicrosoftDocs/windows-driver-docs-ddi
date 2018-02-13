---
UID: NS:d3dumddi._D3DDDIARG_RENDERSTATE
title: "_D3DDDIARG_RENDERSTATE"
author: windows-driver-content
description: The D3DDDIARG_RENDERSTATE structure describes how to update a specific render state.
old-location: display\d3dddiarg_renderstate.htm
old-project: display
ms.assetid: 177a2578-2bd4-4a11-a3fd-fec226a64c22
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIARG_RENDERSTATE, _D3DDDIARG_RENDERSTATE, d3dumddi/D3DDDIARG_RENDERSTATE, D3DDDIARG_RENDERSTATE structure [Display Devices], display.d3dddiarg_renderstate, UMDisplayDriver_param_Structs_4d558ee2-a265-4973-90d4-917170d01ef3.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_RENDERSTATE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_RENDERSTATE
---

# _D3DDDIARG_RENDERSTATE structure


## -description


The D3DDDIARG_RENDERSTATE structure describes how to update a specific render state. 


## -syntax


````
typedef struct _D3DDDIARG_RENDERSTATE {
  D3DDDIRENDERSTATETYPE State;
  UINT                  Value;
} D3DDDIARG_RENDERSTATE;
````


## -struct-fields




### -field State

[in] A D3DDDIRENDERSTATETYPE-typed value that indicates the render state to be updated. For a definition of each value, see the corresponding value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549036">D3DRENDERSTATETYPE</a> enumeration type in the DirectX documentation.


### -field Value

[in] The value to which the driver should update the render state that is identified by the <b>State</b> member. For more information about values that can be updated for each render state, see the definition of the corresponding render state in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549036">D3DRENDERSTATETYPE</a> enumeration type in the DirectX documentation.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setrenderstate.md">SetRenderState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_RENDERSTATE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

