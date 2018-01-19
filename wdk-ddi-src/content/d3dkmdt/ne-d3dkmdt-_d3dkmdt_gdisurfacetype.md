---
UID: NE:d3dkmdt._D3DKMDT_GDISURFACETYPE
title: _D3DKMDT_GDISURFACETYPE
author: windows-driver-content
description: The D3DKMDT_GDISURFACETYPE enumeration indicates the type of lockable surface that is used by the Desktop Window Manager (DWM) for redirection.
old-location: display\d3dkmdt_gdisurfacetype.htm
old-project: display
ms.assetid: b1c8fc0a-b877-4321-85b9-0c5c174ffc45
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMDT_GDISURFACETYPE, D3DKMDT_GDISURFACETYPE
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
req.alt-api: D3DKMDT_GDISURFACETYPE
req.alt-loc: d3dkmdt.h
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
req.typenames: D3DKMDT_GDISURFACETYPE
---

# _D3DKMDT_GDISURFACETYPE enumeration



## -description
The D3DKMDT_GDISURFACETYPE enumeration indicates the type of lockable surface that is used by the Desktop Window Manager (DWM) for redirection.



## -syntax

````
typedef enum _D3DKMDT_GDISURFACETYPE { 
  D3DKMDT_GDISURFACE_INVALID                          = 0,
  D3DKMDT_GDISURFACE_TEXTURE                          = 1,
  D3DKMDT_GDISURFACE_STAGING_CPUVISIBLE               = 2,
  D3DKMDT_GDISURFACE_STAGING                          = 3,
  D3DKMDT_GDISURFACE_LOOKUPTABLE                      = 4,
  D3DKMDT_GDISURFACE_EXISTINGSYSMEM                   = 5,
  D3DKMDT_GDISURFACE_TEXTURE_CPUVISIBLE               = 6,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
  D3DKMDT_GDISURFACE_TEXTURE_CROSSADAPTER             = 7,
  D3DKMDT_GDISURFACE_TEXTURE_CPUVISIBLE_CROSSADAPTER  = 8

#endif } D3DKMDT_GDISURFACETYPE;
````


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
Its pitch value and surface address must be aligned to the value of the <b>AlignmentShift</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_presentationcaps.md">DXGK_PRESENTATIONCAPS</a> structure (that is, <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>-&gt;PresentationCaps.AlignmentShift).

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
It is used only during processing of commands that are specified by the <b>ClearTypeBlend</b> and <b>OpCode</b>.DXGK_GDIOP_BITBLT (copy-only) members of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_renderkm_command.md">DXGK_RENDERKM_COMMAND</a> structure.

</li>
<li>
The format is defined by the D3DDDIFMT_A8 value of the <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a> enumeration.

</li>
<li>
The gamma lookup allocation is created one time and never changes after it is initialized. The allocation is initialized in D3DDDIFMT_A8 format by issuing a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_renderkm_command.md">DXGK_RENDERKM_COMMAND</a>-&gt;Opcode.DXGK_GDIOP_BITBLT command from a D3DKMDT_GDISURFACE_STAGING_CPUVISIBLE surface.

</li>
</ul>

### -field D3DKMDT_GDISURFACE_EXISTINGSYSMEM

Indicates that the surface has the following properties:

<ul>
<li>
It is visible to the CPU. The allocation must be a linear format and in a cache-coherent GPU aperture segment.

</li>
<li>
Its pitch value and surface address must be aligned to the value of the <b>AlignmentShift</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_presentationcaps.md">DXGK_PRESENTATIONCAPS</a> structure (that is, <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>-&gt;PresentationCaps.AlignmentShift).

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
Its pitch must be returned by the display miniport driver in the <b>Pitch</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_gdisurfacedata.md">D3DKMDT_GDISURFACEDATA</a> structure.

</li>
<li>
The pitch and height must have the required alignment for the cross-adapter resource. You can use the <b>D3DKMT_CROSS_ADAPTER_RESOURCE_PITCH_ALIGNMENT</b> and <b>D3DKMT_CROSS_ADAPTER_RESOURCE_HEIGHT_ALIGNMENT</b> constants to validate that the driver returns the correct pitch and height for the cross-adapter resource. These constants are defined in D3dukmdt.h.

</li>
</ul>
Supported starting with Windows 8.1.


### -field D3DKMDT_GDISURFACE_TEXTURE_CPUVISIBLE_CROSSADAPTER

Reserved for system use. Do not use this value in your driver.

Supported starting with Windows 8.1.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_gdisurfacedata.md">D3DKMDT_GDISURFACEDATA</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_presentationcaps.md">DXGK_PRESENTATIONCAPS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_renderkm_command.md">DXGK_RENDERKM_COMMAND</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_GDISURFACETYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

