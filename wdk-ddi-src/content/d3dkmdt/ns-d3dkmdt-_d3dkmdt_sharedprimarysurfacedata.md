---
UID: NS:d3dkmdt._D3DKMDT_SHAREDPRIMARYSURFACEDATA
title: "_D3DKMDT_SHAREDPRIMARYSURFACEDATA"
author: windows-driver-content
description: The D3DKMDT_SHAREDPRIMARYSURFACEDATA structure describes a shared primary surface.
old-location: display\d3dkmdt_sharedprimarysurfacedata.htm
old-project: display
ms.assetid: edf59add-0155-4619-9c7c-fdb63b954f85
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMDT_SHAREDPRIMARYSURFACEDATA, D3DKMDT_SHAREDPRIMARYSURFACEDATA structure [Display Devices], DmStructs_5296d822-1a79-459e-809c-2d7381a964b8.xml, _D3DKMDT_SHAREDPRIMARYSURFACEDATA, d3dkmdt/D3DKMDT_SHAREDPRIMARYSURFACEDATA, display.d3dkmdt_sharedprimarysurfacedata
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
-	D3DKMDT_SHAREDPRIMARYSURFACEDATA
product: Windows
targetos: Windows
req.typenames: D3DKMDT_SHAREDPRIMARYSURFACEDATA
---

# _D3DKMDT_SHAREDPRIMARYSURFACEDATA structure


## -description


The D3DKMDT_SHAREDPRIMARYSURFACEDATA structure describes a shared primary surface.


## -syntax


````
typedef struct _D3DKMDT_SHAREDPRIMARYSURFACEDATA {
  UINT                           Width;
  UINT                           Height;
  D3DDDIFORMAT                   Format;
  D3DDDI_RATIONAL                RefreshRate;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
} D3DKMDT_SHAREDPRIMARYSURFACEDATA;
````


## -struct-fields




### -field Width

[in] The width of the surface, in pixels. The driver returns the width value.


### -field Height

[in] The height of the surface, in pixels. The driver returns the height value.


### -field Format

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the surface. The driver returns the format value.


### -field RefreshRate

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_rational.md">D3DDDI_RATIONAL</a> structure that indicates the refresh rate that the shared primary surface was created with.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the surface is located on. 


## -remarks



Multiple processes can lock a shared primary surface. The video memory manager pins the standard allocation for the shared primary surface in video memory so the digital-to-analog converter (DAC) is guaranteed to always scan-out the appropriate data.




## -see-also

<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_standardallocation_type.md">D3DKMDT_STANDARDALLOCATION_TYPE</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_rational.md">D3DDDI_RATIONAL</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata.md">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_SHAREDPRIMARYSURFACEDATA structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

