---
UID: NS:d3dkmdt._D3DKMDT_STAGINGSURFACEDATA
title: "_D3DKMDT_STAGINGSURFACEDATA" (d3dkmdt.h)
description: The D3DKMDT_STAGINGSURFACEDATA structure describes the lockable staging surface that data is transferred into from an application's back buffer.
old-location: display\d3dkmdt_stagingsurfacedata.htm
tech.root: display
ms.assetid: 6de0bd43-8f19-47f7-adbf-76ea312bd990
ms.date: 05/10/2018
ms.keywords: D3DKMDT_STAGINGSURFACEDATA, D3DKMDT_STAGINGSURFACEDATA structure [Display Devices], DmStructs_94b90abc-85db-4439-a20b-9edeb1a69733.xml, _D3DKMDT_STAGINGSURFACEDATA, d3dkmdt/D3DKMDT_STAGINGSURFACEDATA, display.d3dkmdt_stagingsurfacedata
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	D3DKMDT_STAGINGSURFACEDATA
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_STAGINGSURFACEDATA
---

# _D3DKMDT_STAGINGSURFACEDATA structure


## -description


The D3DKMDT_STAGINGSURFACEDATA structure describes the lockable staging surface that data is transferred into from an application's back buffer.


## -struct-fields




### -field Width

[in] The width of the staging buffer, in pixels.


### -field Height

[in] The height of the staging buffer, in pixels.


### -field Pitch

[out] The width of the staging buffer, in bytes. The driver must return the pitch value because the staging buffer is lockable. 


## -remarks



The D3DKMDT_STAGINGSURFACEDATA structure is passed by the Microsoft DirectX graphics kernel subsystem in a call to the display miniport driver's <a href="https://msdn.microsoft.com/38a9859f-ed9f-41a5-9bf1-c734480499ea">DxgkDdiGetStandardAllocationDriverData</a> function to generate a description of a lockable staging surface. The graphics subsystem calls the display miniport driver's <a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a> function to issue bit-block transfer (bitblt) requests to transfer data from an application's back buffer into the staging surface. The staging surface is then locked and read by the CPU. 

A staging surface is potentially created for the present operation when a direct bit-block transfer to the primary surface is not possible (for example, in multiple-monitor or sprites cases). 

This staging surface is always created as an 8-bits-per-color RGB pixel format (which is specified by the D3DDDIFMT_X8R8G8B8 value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a> enumeration). Because the dimensions of the staging surface always match the dimensions of the back buffer, no stretch or shrink operation is required for the present operation to the staging surface.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546589">D3DKMDT_STANDARDALLOCATION_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557559">DXGKARG_CREATEALLOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557598">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>



<a href="https://msdn.microsoft.com/38a9859f-ed9f-41a5-9bf1-c734480499ea">DxgkDdiGetStandardAllocationDriverData</a>



<a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a>



<a href="https://msdn.microsoft.com/e90683b4-64b6-4018-96a5-b50118df3367">Present</a>
 

 

