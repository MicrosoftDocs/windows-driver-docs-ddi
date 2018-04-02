---
UID: NE:d3dkmdt._D3DKMDT_GDISURFACETYPE
title: "_D3DKMDT_GDISURFACETYPE"
author: windows-driver-content
description: The D3DKMDT_GDISURFACETYPE enumeration indicates the type of lockable surface that is used by the Desktop Window Manager (DWM) for redirection.
old-location: display\d3dkmdt_gdisurfacetype.htm
old-project: display
ms.assetid: b1c8fc0a-b877-4321-85b9-0c5c174ffc45
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMDT_GDISURFACETYPE, D3DKMDT_GDISURFACETYPE enumeration [Display Devices], D3DKMDT_GDISURFACE_EXISTINGSYSMEM, D3DKMDT_GDISURFACE_INVALID, D3DKMDT_GDISURFACE_LOOKUPTABLE, D3DKMDT_GDISURFACE_STAGING, D3DKMDT_GDISURFACE_STAGING_CPUVISIBLE, D3DKMDT_GDISURFACE_TEXTURE, D3DKMDT_GDISURFACE_TEXTURE_CPUVISIBLE, D3DKMDT_GDISURFACE_TEXTURE_CPUVISIBLE_CROSSADAPTER, D3DKMDT_GDISURFACE_TEXTURE_CROSSADAPTER, DmEnums_5e870c41-1496-48ff-bddd-f01a2f9e36e6.xml, _D3DKMDT_GDISURFACETYPE, d3dkmdt/D3DKMDT_GDISURFACETYPE, d3dkmdt/D3DKMDT_GDISURFACE_EXISTINGSYSMEM, d3dkmdt/D3DKMDT_GDISURFACE_INVALID, d3dkmdt/D3DKMDT_GDISURFACE_LOOKUPTABLE, d3dkmdt/D3DKMDT_GDISURFACE_STAGING, d3dkmdt/D3DKMDT_GDISURFACE_STAGING_CPUVISIBLE, d3dkmdt/D3DKMDT_GDISURFACE_TEXTURE, d3dkmdt/D3DKMDT_GDISURFACE_TEXTURE_CPUVISIBLE, d3dkmdt/D3DKMDT_GDISURFACE_TEXTURE_CPUVISIBLE_CROSSADAPTER, d3dkmdt/D3DKMDT_GDISURFACE_TEXTURE_CROSSADAPTER, display.d3dkmdt_gdisurfacetype
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	D3DKMDT_GDISURFACETYPE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_GDISURFACETYPE
---

# _D3DKMDT_GDISURFACETYPE enumeration


## -description


The D3DKMDT_GDISURFACETYPE enumeration indicates the type of lockable surface that is used by the Desktop Window Manager (DWM) for redirection.


## -enum-fields




### -field D3DKMDT_GDISURFACE_INVALID

The driver should not see this value.


### -field D3DKMDT_GDISURFACE_TEXTURE

Indicates that the surface has the following properties:

<ul>
<li>
It has a one-level texture.

</li>
<li>
It is not visible to the CPU, and the video memory manager will create it as a shared surface.

</li>
<li>
It is opened by a user-mode driver and used as a texture during DWM composition.

</li>
<li>
It is used by a user-mode driver as a render target for DirectX rendering.

</li>
<li>
It is used as a source or destination surface in GDI hardware-accelerated operations.

</li>
</ul>

### -field D3DKMDT_GDISURFACE_STAGING_CPUVISIBLE

Indicates that the surface has the following properties:

<ul>
<li>
It is visible to the CPU and will be extensively used by the CPU. The allocation must be a linear format and in a cache-coherent GPU aperture segment.

</li>
<li>
It is used as a source surface in GDI hardware-accelerated operations.

</li>
<li>
It is used as a destination surface in bitblt (copy-only) GDI operations.

</li>
<li>
Its pitch must be returned by the display miniport driver.

</li>
<li>
Its pitch value and surface address must be aligned to the value of the <b>AlignmentShift</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562004">DXGK_PRESENTATIONCAPS</a> structure (that is, <a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>-&gt;PresentationCaps.AlignmentShift).

</li>
</ul>

### -field D3DKMDT_GDISURFACE_STAGING

Indicates that the surface has the following properties:

<ul>
<li>
It is not visible to the CPU.

</li>
<li>
It is used as a source or destination surface in GDI hardware-accelerated operations.

</li>
<li>
It is used as a source or destination surface in GDI bitblt (copy-only) operations.

</li>
</ul>

### -field D3DKMDT_GDISURFACE_LOOKUPTABLE

Indicates that the surface has the following properties:

<ul>
<li>
It is not visible to the CPU.

</li>
<li>
It is used only during processing of commands that are specified by the <b>ClearTypeBlend</b> and <b>OpCode</b>.DXGK_GDIOP_BITBLT (copy-only) members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562026">DXGK_RENDERKM_COMMAND</a> structure.

</li>
<li>
The format is defined by the D3DDDIFMT_A8 value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a> enumeration.

</li>
<li>
The gamma lookup allocation is created one time and never changes after it is initialized. The allocation is initialized in D3DDDIFMT_A8 format by issuing a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562026">DXGK_RENDERKM_COMMAND</a>-&gt;Opcode.DXGK_GDIOP_BITBLT command from a D3DKMDT_GDISURFACE_STAGING_CPUVISIBLE surface.

</li>
</ul>

### -field D3DKMDT_GDISURFACE_EXISTINGSYSMEM

Indicates that the surface has the following properties:

<ul>
<li>
It is visible to the CPU. The allocation must be a linear format and in a cache-coherent GPU aperture segment.

</li>
<li>
Its pitch value and surface address must be aligned to the value of the <b>AlignmentShift</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562004">DXGK_PRESENTATIONCAPS</a> structure (that is, <a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>-&gt;PresentationCaps.AlignmentShift).

</li>
<li>
The surface address is passed to the driver.

</li>
<li>
This value is used in the same way as the D3DKMDT_GDISURFACE_STAGING_CPUVISIBLE value.

</li>
</ul>

### -field D3DKMDT_GDISURFACE_TEXTURE_CPUVISIBLE

Reserved for system use. Do not use this value in your driver.

Supported starting with Windows 8.


### -field D3DKMDT_GDISURFACE_TEXTURE_CROSSADAPTER

Indicates that the surface has the following properties:

<ul>
<li>
It is not visible to the CPU, and the video memory manager will create it as a shared cross-adapter surface.

</li>
<li>
Its pitch must be returned by the display miniport driver in the <b>Pitch</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546021">D3DKMDT_GDISURFACEDATA</a> structure.

</li>
<li>
The pitch and height must have the required alignment for the cross-adapter resource. You can use the <b>D3DKMT_CROSS_ADAPTER_RESOURCE_PITCH_ALIGNMENT</b> and <b>D3DKMT_CROSS_ADAPTER_RESOURCE_HEIGHT_ALIGNMENT</b> constants to validate that the driver returns the correct pitch and height for the cross-adapter resource. These constants are defined in D3dukmdt.h.

</li>
</ul>
Supported starting with Windows 8.1.


### -field D3DKMDT_GDISURFACE_TEXTURE_CPUVISIBLE_CROSSADAPTER

Reserved for system use. Do not use this value in your driver.

Supported starting with Windows 8.1.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546021">D3DKMDT_GDISURFACEDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562004">DXGK_PRESENTATIONCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562026">DXGK_RENDERKM_COMMAND</a>
 

 

