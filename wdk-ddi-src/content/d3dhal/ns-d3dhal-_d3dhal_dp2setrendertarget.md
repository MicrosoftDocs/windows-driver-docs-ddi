---
UID: NS:d3dhal._D3DHAL_DP2SETRENDERTARGET
title: "_D3DHAL_DP2SETRENDERTARGET"
author: windows-driver-content
description: The D3DHAL_DP2SETRENDERTARGET structure is used with the D3DDP2OP_SETRENDERTARGET opcode to map a new rendering target surface and depth buffer in the current context.
old-location: display\d3dhal_dp2setrendertarget.htm
old-project: display
ms.assetid: 0ececf46-23a4-456b-8305-b9cd0ffba4b6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*LPD3DHAL_DP2SETRENDERTARGET, D3DHAL_DP2SETRENDERTARGET, D3DHAL_DP2SETRENDERTARGET structure [Display Devices], LPD3DHAL_DP2SETRENDERTARGET, LPD3DHAL_DP2SETRENDERTARGET structure pointer [Display Devices], _D3DHAL_DP2SETRENDERTARGET, d3dhal/D3DHAL_DP2SETRENDERTARGET, d3dhal/LPD3DHAL_DP2SETRENDERTARGET, d3dstrct_d3f81bd9-d8fd-4560-b8b3-61af41d4a13b.xml, display.d3dhal_dp2setrendertarget"
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
-	D3DHAL_DP2SETRENDERTARGET
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETRENDERTARGET
---

# _D3DHAL_DP2SETRENDERTARGET structure


## -description


The D3DHAL_DP2SETRENDERTARGET structure is used with the D3DDP2OP_SETRENDERTARGET opcode to map a new rendering target surface and depth buffer in the current context.


## -syntax


````
typedef struct _D3DHAL_DP2SETRENDERTARGET {
  DWORD hRenderTarget;
  DWORD hZBuffer;
} D3DHAL_DP2SETRENDERTARGET, *LPD3DHAL_DP2SETRENDERTARGET;
````


## -struct-fields




### -field hRenderTarget

Specifies a handle to the rendering target.


### -field hZBuffer

Specifies a handle to the depth buffer.


## -remarks



The driver should carry out the following tasks in response to a D3DDP2OP_SETRENDERTARGET opcode in the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> command stream:

<ol>
<li>
Store the rendering target identified by <b>hRenderTarget</b> in the driver's context. 

</li>
<li>
Store the depth buffer identified by <b>hZBuffer</b> in the driver's context. 

</li>
</ol>
See the <i>p3samp</i> sample driver that ships with the Microsoft Windows Driver Development Kit (DDK) for more implementation details.




## -see-also

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



D3DDP2OP_SETRENDERTARGET



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SETRENDERTARGET structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

