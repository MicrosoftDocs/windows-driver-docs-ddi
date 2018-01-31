---
UID: NS:d3dhal._D3DHAL_DP2VERTEXSHADER
title: "_D3DHAL_DP2VERTEXSHADER"
author: windows-driver-content
description: DirectX 8.0 and later versions only. The D3DHAL_DP2VERTEXSHADER structure sets the current vertex shader, or deletes a vertex shader, depending on the opcode received (D3DDP2OP_SETVERTEXSHADER or D3DDP2OP_DELETEVERTEXSHADER) by D3dDrawPrimitives2.
old-location: display\d3dhal_dp2vertexshader.htm
old-project: display
ms.assetid: 9207768b-530a-49d5-999e-0e8eb6bd1fe5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dhal/D3DHAL_DP2VERTEXSHADER, d3dstrct_84401bfa-f79d-4128-9989-1223284f25b0.xml, D3DHAL_DP2VERTEXSHADER, *LPD3DHAL_DP2VERTEXSHADER, D3DHAL_DP2VERTEXSHADER structure [Display Devices], LPD3DHAL_DP2VERTEXSHADER, d3dhal/LPD3DHAL_DP2VERTEXSHADER, LPD3DHAL_DP2VERTEXSHADER structure pointer [Display Devices], _D3DHAL_DP2VERTEXSHADER, display.d3dhal_dp2vertexshader
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dhal.h
apiname:
-	D3DHAL_DP2VERTEXSHADER
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2VERTEXSHADER
---

# _D3DHAL_DP2VERTEXSHADER structure


## -description



   DirectX 8.0 and later versions only.
   

The D3DHAL_DP2VERTEXSHADER structure sets the current vertex shader, or deletes a vertex shader, depending on the opcode received (D3DDP2OP_SETVERTEXSHADER or D3DDP2OP_DELETEVERTEXSHADER) by <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.


## -syntax


````
typedef struct _D3DHAL_DP2VERTEXSHADER {
  DWORD dwHandle;
} D3DHAL_DP2VERTEXSHADER, *LPD3DHAL_DP2VERTEXSHADER;
````


## -struct-fields




#### - dwHandle



#### 



#### 



#### 



## -remarks


All DirectX 8.0 level drivers must support the D3DDP2OP_SETVERTEXSHADER token because it is sent even if the driver does not support programmable vertex processing. In that case, however, the shader handle is always an FVF code indicating fixed function processing of the vertex data. The driver should use the FVF code stored in the <b>dwHandle</b> member as the format of the vertex data in stream zero. A driver that does support programmable vertex processing must examine the handle to determine whether it refers to a shader previously created with D3DDP2OP_CREATEVERTEXSHADER or an FVF code and take the appropriate action.

Pixel and vertex shaders are orthogonal. Thus, if a legacy FVF code is selected as the current vertex shader this does not imply legacy pixel processing. In order to reset pixel processing to a subprogrammable mode the current pixel shader must also be set to zero. Care should be taken in the driver to only reset vertex processing state to a fixed function mode and not pixel processing state when the vertex shader is set to an FVF code.

When switching from fixed function vertex processing to programmable vertex processing, the values of legacy render state and matrices should be preserved. If and when a switch from programmable to fixed function vertex processing occurs (the driver receives a D3DDP2OP_SETVERTEXSHADER with an FVF as the shader handle), that preserved state should be restored.

When switching between programmable shaders, any constant register that has a value specified in the definition of that shader should be set to that value. The values of all other constant registers should remain unchanged.

For D3DDP2OP_SETVERTEXSHADERDECL operations, the runtime specifies a legacy FVF code or a DirectX 9.0 declaration handle in the <b>dwHandle</b> member. The runtime indicates a DirectX 9.0 declaration handle by setting bit 0 of the handle. For D3DDP2OP_SETVERTEXSHADERFUNC operations, the runtime sets <b>dwHandle</b> to zero to indicate a fixed function pipeline.



## -see-also

D3DDP2OP_CREATEVERTEXSHADER

D3DDP2OP_SETSTREAMSOURCE

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2createvertexshader.md">D3DHAL_DP2CREATEVERTEXSHADER</a>

D3DDP2OP_DELETEVERTEXSHADERDECL

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2setvertexshaderconst.md">D3DHAL_DP2SETVERTEXSHADERCONST</a>

D3DDP2OP_SETVERTEXSHADERDECL

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>

D3DDP2OP_DELETEVERTEXSHADERFUNC

D3DDP2OP_SETVERTEXSHADER

D3DDP2OP_DELETEVERTEXSHADER

D3DDP2OP_SETVERTEXSHADERFUNC

D3DDP2OP_SETSTREAMSOURCEUM

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2VERTEXSHADER structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

