---
UID: NC:d3dumddi.PFND3DDDI_BLT
title: PFND3DDDI_BLT
description: The Blt function copies the contents of a source surface to a destination surface.
old-location: display\blt.htm
tech.root: display
ms.assetid: e87576c6-0173-4d8e-bbaf-b82e2907140a
ms.date: 05/10/2018
ms.keywords: Blt, Blt callback function [Display Devices], PFND3DDDI_BLT, PFND3DDDI_BLT callback, UserModeDisplayDriver_Functions_d2dfd3c9-e7e0-4953-bc88-3d3330aff161.xml, d3dumddi/Blt, display.blt
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
-	Blt
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_BLT callback function


## -description


The <b>Blt</b> function copies the contents of a source surface to a destination surface.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *

*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542884">D3DDDIARG_BLT</a> structure that describes the parameters of the bit-block transfer (bitblt).


## -returns



<b>Blt</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The bitblt for the resource is successfully performed. | 
| **E_OUTOFMEMORY** | [Blt](https://msdn.microsoft.com/e87576c6-0173-4d8e-bbaf-b82e2907140a)  could not allocate the required memory for it to complete. | 


## -remarks



The Microsoft Direct3D runtime calls the user-mode display driver's <b>Blt</b> function to copy the contents of a source surface to a destination surface. After mapping the surface references to allocation references, the user-mode display driver should issue the appropriate hardware commands. If either the source or destination allocation is in system memory, the user-mode display driver might be required to synchronize (that is, call the <a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a> function) if the outstanding hardware command stream contains references to the system-memory allocation. If both the source and destination allocations are in system memory, the driver should synchronize as necessary but should not copy the contents of the source surface. The Direct3D runtime copies the contents after the call to <b>pfnRenderCb</b> returns. 

The user-mode display driver must handle the following conditions that might occur during a copy operation:

<ul>
<li>
The destination and source surfaces are part of the same resource (that is, the <b>hSrcResource</b> and <b>hDstResource</b> members of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542884">D3DDDIARG_BLT</a> specify handles to the same resource).

</li>
<li>
The source and destination rectangles overlap (that is, the coordinates of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structures in the <b>SrcRect</b> and <b>DstRect</b> members of D3DDDIARG_BLT overlap).

</li>
</ul>
The user-mode display driver must handle all of the bitblt to and from video memory, including bitblt from video memory to system memory. If the user-mode display driver cannot use the graphics processing unit (GPU) to issue a bitblt from video memory to system memory, the user-mode display driver can copy the data by using the CPU.

The user-mode display driver must support colorkeying only with formats that were introduced before Microsoft DirectX 8.0. For formats that were introduced in DirectX 8.0 and later runtimes, colorkeying support is not required.

The type of bitblt to perform is indicated through the bit-field flags that are specified in the <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542884">D3DDDIARG_BLT</a>. Video memory to video memory bitblts can include colorkeying, stretching, mirroring, and linear-to-sRGB format conversion. System memory to video memory bitblts can include stretching and linear-to-sRGB format conversion; however, these types of bitblts never include mirroring or colorkeying. All video memory to system memory bitblts and system memory to system memory bitblts are straight copies only; that is, these types of bitblts never include stretching, mirroring, colorkeying, or linear-to-sRGB format conversion. For more information about sRGB format, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=10112">sRGB</a> website.

For more information about rules that the <b>Blt</b> function must follow when converting depth-stencil values, see <a href="https://msdn.microsoft.com/b83d4e6d-5645-49ab-bbb0-c694f1410cba">Copying Depth-Stencil Values</a>.

The Direct3D runtime can call the user-mode display driver's <b>Blt</b> function to copy the contents of any source surface type (such as, offscreen-plain type, render-target type, or texture type) to any other destination surface type. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542884">D3DDDIARG_BLT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a>
 

 

