---
UID: NC:d3dumddi.PFND3DDDI_DRAWINDEXEDPRIMITIVE2
title: PFND3DDDI_DRAWINDEXEDPRIMITIVE2
author: windows-driver-content
description: The DrawIndexedPrimitive2 function draws indexed primitives that the Microsoft Direct3D runtime has transformed the index data in.
old-location: display\drawindexedprimitive2.htm
old-project: display
ms.assetid: f12af70c-a6f2-42da-be62-1cfeb90b6239
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DrawIndexedPrimitive2
req.alt-loc: d3dumddi.h
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_DRAWINDEXEDPRIMITIVE2 callback



## -description
The <b>DrawIndexedPrimitive2</b> function draws indexed primitives that the Microsoft Direct3D runtime has transformed the index data in.



## -prototype

````
PFND3DDDI_DRAWINDEXEDPRIMITIVE2 DrawIndexedPrimitive2;

__checkReturn HRESULT APIENTRY DrawIndexedPrimitive2(
  _In_           HANDLE                          hDevice,
  _In_     const D3DDDIARG_DRAWINDEXEDPRIMITIVE2 *pData,
  _In_           UINT                            dwIndicesSize,
  _In_     const VOID                            *pIndexBuffer,
  _In_opt_ const UINT                            *pFlagBuffer
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawindexedprimitive2.md">D3DDDIARG_DRAWINDEXEDPRIMITIVE2</a> structure that describes the primitive to draw.


### -param dwIndicesSize [in]

 The size, in bytes, of indexes in the buffer that <i>pIndexBuffer</i> points to. This size is 2 or 4 bytes. 


### -param pIndexBuffer [in]

 A pointer to a buffer of index data to be drawn.


### -param pFlagBuffer [in, optional]

 A pointer to a 32-bit value that contains triangle-edge flags, which are used only during line-fill mode. The first three bits (0/1/2) of the 32-bit value specify how the three edges of the corresponding triangle are rendered. If a bit is set to 1, its associated triangle edge is rendered; otherwise, the edge is not rendered.

If the pointer is <b>NULL</b>, the user-mode display driver should use its fast path to draw primitives. 


## -returns
<b>DrawIndexedPrimitive2</b> returns S_OK or an appropriate error result if the primitive is not successfully drawn.


## -remarks
Stream zero contains transform indices and is the only stream that should be accessed. 

When the Microsoft Direct3D runtime specifies triangle-edge flags in the value that the <i>pFlagBuffer</i> parameter points to, the runtime also specifies to draw only one triangle (that is, the runtime specifies the D3DPT_TRIANGLELIST value in the <b>PrimitiveType</b> member and 0x00000001 in the <b>PrimitiveCount</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawindexedprimitive2.md">D3DDDIARG_DRAWINDEXEDPRIMITIVE2</a> structure that the <i>pData</i> parameter points to).


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawindexedprimitive2.md">D3DDDIARG_DRAWINDEXEDPRIMITIVE2</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawindexedprimitive.md">DrawIndexedPrimitive</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DRAWINDEXEDPRIMITIVE2 callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

