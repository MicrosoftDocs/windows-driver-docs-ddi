---
UID: NS:d3dkmdt._D3DKMDT_SHADOWSURFACEDATA
title: "_D3DKMDT_SHADOWSURFACEDATA"
author: windows-driver-content
description: The D3DKMDT_SHADOWSURFACEDATA structure describes a lockable shadow surface, which matches the primary surface in format and resolution for a given display mode.
old-location: display\d3dkmdt_shadowsurfacedata.htm
old-project: display
ms.assetid: 1b7f6a39-b0d3-4a0b-b030-b7fef3ab58d6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmdt_shadowsurfacedata, d3dkmdt/D3DKMDT_SHADOWSURFACEDATA, DmStructs_645dbefc-137b-47c5-aa4b-de9037d71182.xml, D3DKMDT_SHADOWSURFACEDATA, D3DKMDT_SHADOWSURFACEDATA structure [Display Devices], _D3DKMDT_SHADOWSURFACEDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	D3DKMDT_SHADOWSURFACEDATA
product: Windows
targetos: Windows
req.typenames: D3DKMDT_SHADOWSURFACEDATA
---

# _D3DKMDT_SHADOWSURFACEDATA structure


## -description


The D3DKMDT_SHADOWSURFACEDATA structure describes a lockable shadow surface, which matches the primary surface in format and resolution for a given display mode.


## -syntax


````
typedef struct _D3DKMDT_SHADOWSURFACEDATA {
  UINT         Width;
  UINT         Height;
  D3DDDIFORMAT Format;
  UINT         Pitch;
} D3DKMDT_SHADOWSURFACEDATA;
````


## -struct-fields




### -field Width

[in] The width of the surface, in pixels. The driver returns the width value.


### -field Height

[in] The height of the surface, in pixels. The driver returns the height value.


### -field Format

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the surface. The driver returns the format value.


### -field Pitch

[out] The width of the surface, in bytes. The driver must return the pitch value because the shadow surface is lockable.


## -remarks


The D3DKMDT_SHADOWSURFACEDATA structure is passed by the Microsoft DirectX graphics kernel subsystem in a call to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md">DxgkDdiGetStandardAllocationDriverData</a> function to generate a description of a lockable shadow surface. The DirectX graphics kernel subsystem uses the description in a call to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function to create the lockable shadow surface.

The CPU draws into the locked shadow surface, unlocks the shadow surface, and then issues bit-block transfer (bitblt) requests through the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a> function from the shadow surface to the matched shared primary surface. Bit-block transfer requests are also issued to transfer data from a shared primary surface into the shadow surface. 

A color conversion, stretch, or shrink operation is not required when copying data from or to a shadow surface because the source and destination formats and dimensions of shadow and shared primary surfaces always match.



## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata.md">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>

<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_standardallocation_type.md">D3DKMDT_STANDARDALLOCATION_TYPE</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md">DxgkDdiGetStandardAllocationDriverData</a>

<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_SHADOWSURFACEDATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

