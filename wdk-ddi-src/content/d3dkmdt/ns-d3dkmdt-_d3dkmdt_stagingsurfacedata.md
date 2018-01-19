---
UID: NS:d3dkmdt._D3DKMDT_STAGINGSURFACEDATA
title: _D3DKMDT_STAGINGSURFACEDATA
author: windows-driver-content
description: The D3DKMDT_STAGINGSURFACEDATA structure describes the lockable staging surface that data is transferred into from an application's back buffer.
old-location: display\d3dkmdt_stagingsurfacedata.htm
old-project: display
ms.assetid: 6de0bd43-8f19-47f7-adbf-76ea312bd990
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMDT_STAGINGSURFACEDATA, D3DKMDT_STAGINGSURFACEDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_STAGINGSURFACEDATA
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
req.irql: 
req.typenames: D3DKMDT_STAGINGSURFACEDATA
---

# _D3DKMDT_STAGINGSURFACEDATA structure



## -description
The D3DKMDT_STAGINGSURFACEDATA structure describes the lockable staging surface that data is transferred into from an application's back buffer.



## -syntax

````
typedef struct _D3DKMDT_STAGINGSURFACEDATA {
  UINT Width;
  UINT Height;
  UINT Pitch;
} D3DKMDT_STAGINGSURFACEDATA;
````


## -struct-fields

### -field Width

[in] The width of the staging buffer, in pixels.


### -field Height

[in] The height of the staging buffer, in pixels.


### -field Pitch

[out] The width of the staging buffer, in bytes. The driver must return the pitch value because the staging buffer is lockable. 


## -remarks
The D3DKMDT_STAGINGSURFACEDATA structure is passed by the Microsoft DirectX graphics kernel subsystem in a call to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md">DxgkDdiGetStandardAllocationDriverData</a> function to generate a description of a lockable staging surface. The graphics subsystem calls the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a> function to issue bit-block transfer (bitblt) requests to transfer data from an application's back buffer into the staging surface. The staging surface is then locked and read by the CPU. 

A staging surface is potentially created for the present operation when a direct bit-block transfer to the primary surface is not possible (for example, in multiple-monitor or sprites cases). 

This staging surface is always created as an 8-bits-per-color RGB pixel format (which is specified by the D3DDDIFMT_X8R8G8B8 value from the <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a> enumeration). Because the dimensions of the staging surface always match the dimensions of the back buffer, no stretch or shrink operation is required for the present operation to the staging surface.


## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>
</dt>
<dt>
<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_standardallocation_type.md">D3DKMDT_STANDARDALLOCATION_TYPE</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata.md">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md">DxgkDdiGetStandardAllocationDriverData</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_present.md">Present</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_STAGINGSURFACEDATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

