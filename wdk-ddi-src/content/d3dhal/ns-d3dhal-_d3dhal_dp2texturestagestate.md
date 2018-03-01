---
UID: NS:d3dhal._D3DHAL_DP2TEXTURESTAGESTATE
title: "_D3DHAL_DP2TEXTURESTAGESTATE"
author: windows-driver-content
description: One or more D3DHAL_DP2TEXTURESTAGESTATE structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_TEXTURESTAGESTATE, and are used to set the appropriate texture stage state.
old-location: display\d3dhal_dp2texturestagestate.htm
old-project: display
ms.assetid: 32a671e9-6a31-483f-881d-1c7938dc9405
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*LPD3DHAL_DP2TEXTURESTAGESTATE, D3DHAL_DP2TEXTURESTAGESTATE, D3DHAL_DP2TEXTURESTAGESTATE structure [Display Devices], LPD3DHAL_DP2TEXTURESTAGESTATE, LPD3DHAL_DP2TEXTURESTAGESTATE structure pointer [Display Devices], _D3DHAL_DP2TEXTURESTAGESTATE, d3dhal/D3DHAL_DP2TEXTURESTAGESTATE, d3dhal/LPD3DHAL_DP2TEXTURESTAGESTATE, d3dstrct_3cecbef0-387e-4ec1-aa67-2a6e84b7c78a.xml, display.d3dhal_dp2texturestagestate"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	d3dhal.h
api_name:
-	D3DHAL_DP2TEXTURESTAGESTATE
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2TEXTURESTAGESTATE
---

# _D3DHAL_DP2TEXTURESTAGESTATE structure


## -description


One or more D3DHAL_DP2TEXTURESTAGESTATE structures are parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_TEXTURESTAGESTATE, and are used to set the appropriate texture stage state.


## -syntax


````
typedef struct _D3DHAL_DP2TEXTURESTAGESTATE {
  WORD  wStage;
  WORD  TSState;
  DWORD dwValue;
} D3DHAL_DP2TEXTURESTAGESTATE, *LPD3DHAL_DP2TEXTURESTAGESTATE;
````


## -struct-fields




### -field wStage

Identifies the texture stage where to update the texture state. This member can be an integer in the range 0 through 7, with the highest numbered texture being closest to the frame buffer.


### -field TSState

Specifies a D3DTEXTURESTAGESTATETYPE enumerated value that specifies the texture state to be updated. DirectX 9.0 and later applications can use values in the D3DSAMPLERSTATETYPE enumeration to control the characteristics of sampler texture-related render states. In DirectX 8.0 and earlier, these sampler states were included in the D3DTEXTURESTAGESTATETYPE enumeration. The runtime maps user-mode sampler states (D3DSAMP_<i>Xxx</i>) to kernel-mode D3DTSS_<i>Xxx</i> values so that drivers are not required to process user-mode sampler states. For more information about D3DTEXTURESTAGESTATETYPE and D3DSAMPLERSTATETYPE, see the DirectX SDK documentation.


### -field dwValue

Specifies the value that the driver should update the texture state identified by <b>TSState</b> to.


## -remarks




<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> should process <b>wStateCount</b> D3DHAL_DP2TEXTURESTAGESTATE structures from the command buffer. The value of <b>wStateCount</b> is specified in the D3DHAL_DP2COMMAND structure.

For each D3DHAL_DP2TEXTURESTAGESTATE structure, <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> should update the driver's internal texture state associated with the texture at <b>dwStage</b> to reflect the new value based on <b>TSState</b>.

Drivers that do not support multitexturing should implement support for texture stage 0 only.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_TEXTURESTAGESTATE command and three D3DHAL_DP2TEXTURESTAGESTATE structures. The driver should update stages zero and three of its private texture stage state accordingly.

<img alt="Figure showing a command buffer with a D3DDP2OP_TEXTURESTAGESTATE command and three D3DHAL_DP2TEXTURESTAGESTATE structures " src="images/dp2tss.png"/>



## -see-also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



D3DDP2OP_TEXTURESTAGESTATE



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2TEXTURESTAGESTATE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

