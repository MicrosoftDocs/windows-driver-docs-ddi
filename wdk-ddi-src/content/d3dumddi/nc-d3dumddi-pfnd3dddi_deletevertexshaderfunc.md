---
UID: NC:d3dumddi.PFND3DDDI_DELETEVERTEXSHADERFUNC
title: PFND3DDDI_DELETEVERTEXSHADERFUNC
author: windows-driver-content
description: The DeleteVertexShaderFunc function cleans up driver-side resources that are associated with vertex shader code.
old-location: display\deletevertexshaderfunc.htm
old-project: display
ms.assetid: 780fc47c-bbb9-400a-a2f3-cdce4a18072f
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
req.alt-api: DeleteVertexShaderFunc
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

# PFND3DDDI_DELETEVERTEXSHADERFUNC callback



## -description
The <b>DeleteVertexShaderFunc</b> function cleans up driver-side resources that are associated with vertex shader code.



## -prototype

````
PFND3DDDI_DELETEVERTEXSHADERFUNC DeleteVertexShaderFunc;

__checkReturn HRESULT APIENTRY DeleteVertexShaderFunc(
  _In_ HANDLE hDevice,
  _In_ HANDLE hShaderHandle
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param hShaderHandle [in]

 A handle to the vertex shader code object.


## -returns
<b>DeleteVertexShaderFunc</b> returns S_OK or an appropriate error result if the vertex shader code object is not successfully cleaned up.


## -remarks
The <b>DeleteVertexShaderFunc</b> function notifies the driver about the deletion of the vertex shader code object that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvertexshaderfunc.md">CreateVertexShaderFunc</a> function created. The driver can then clean up any driver-side resources that are associated with the vertex shader code.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvertexshaderfunc.md">CreateVertexShaderFunc</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DELETEVERTEXSHADERFUNC callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

