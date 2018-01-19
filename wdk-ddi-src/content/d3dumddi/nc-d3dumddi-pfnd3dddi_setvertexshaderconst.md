---
UID: NC:d3dumddi.PFND3DDDI_SETVERTEXSHADERCONST
title: PFND3DDDI_SETVERTEXSHADERCONST
author: windows-driver-content
description: The SetVertexShaderConst function sets one or more vertex shader constant registers with floating-point values.
old-location: display\setvertexshaderconst.htm
old-project: display
ms.assetid: 2dbde343-b10a-4357-a2b7-d6b1b1b868f2
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
req.alt-api: SetVertexShaderConst
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

# PFND3DDDI_SETVERTEXSHADERCONST callback



## -description
The <i>SetVertexShaderConst</i> function sets one or more vertex shader constant registers with floating-point values.



## -prototype

````
PFND3DDDI_SETVERTEXSHADERCONST SetVertexShaderConst;

__checkReturn HRESULT APIENTRY SetVertexShaderConst(
  _In_       HANDLE                         hDevice,
  _In_ const D3DDDIARG_SETVERTEXSHADERCONST *pData,
  _In_ const VOID                           *pRegisters
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setvertexshaderconst.md">D3DDDIARG_SETVERTEXSHADERCONST</a> structure that specifies how to set the vertex shader constant registers.


### -param pRegisters [in]

 A pointer to a buffer that contains the floating-point values to copy.


## -returns
<i>SetVertexShaderConst</i> returns S_OK or an appropriate error result if the vertex shader constant registers are not successfully set with floating-point values.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setvertexshaderconst.md">D3DDDIARG_SETVERTEXSHADERCONST</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETVERTEXSHADERCONST callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

