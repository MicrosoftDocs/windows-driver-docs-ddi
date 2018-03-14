---
UID: NC:d3dumddi.PFND3DDDI_CAPTURETOSYSMEM
title: PFND3DDDI_CAPTURETOSYSMEM
author: windows-driver-content
description: The CaptureToSysMem function copies the contents of a capture buffer to a destination surface.
old-location: display\capturetosysmem.htm
old-project: display
ms.assetid: ea2b5338-81cf-4114-bb07-16e8ff4d2b95
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CaptureToSysMem, CaptureToSysMem callback function [Display Devices], PFND3DDDI_CAPTURETOSYSMEM, UserModeDisplayDriver_Functions_9d7270cc-da5e-4c04-8ab6-93b9cfd7a475.xml, d3dumddi/CaptureToSysMem, display.capturetosysmem
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	CaptureToSysMem
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_CAPTURETOSYSMEM callback


## -description


The <b>CaptureToSysMem</b> function copies the contents of a capture buffer to a destination surface.


## -prototype


````
PFND3DDDI_CAPTURETOSYSMEM CaptureToSysMem;

__checkReturn HRESULT APIENTRY CaptureToSysMem(
  _In_       HANDLE                    hDevice,
  _In_ const D3DDDIARG_CAPTURETOSYSMEM *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_capturetosysmem.md">D3DDDIARG_CAPTURETOSYSMEM</a> structure that describes the parameters of the bit-block transfer (bitblt).


## -returns



<b>CaptureToSysMem</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
All resources for the bitblt are in GPU-accessible memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_capturetosysmem.md">CaptureToSysMem</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



The <b>CaptureToSysMem</b> function is similar to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_blt.md">Blt</a> function except that <b>CaptureToSysMem</b> supports copying only from a capture buffer.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_capturetosysmem.md">D3DDDIARG_CAPTURETOSYSMEM</a>



 

 


