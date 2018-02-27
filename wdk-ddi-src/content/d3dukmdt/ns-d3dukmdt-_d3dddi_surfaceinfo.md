---
UID: NS:d3dukmdt._D3DDDI_SURFACEINFO
title: "_D3DDDI_SURFACEINFO"
author: windows-driver-content
description: The D3DDDI_SURFACEINFO structure describes a resource type, such as a surface.
old-location: display\d3dddi_surfaceinfo.htm
old-project: display
ms.assetid: 347edff7-b209-4b60-aabc-5ee7963c8164
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDI_SURFACEINFO, D3DDDI_SURFACEINFO structure [Display Devices], D3D_other_Structs_03e742b5-062c-46d3-bedf-25aee3582dfc.xml, _D3DDDI_SURFACEINFO, d3dukmdt/D3DDDI_SURFACEINFO, display.d3dddi_surfaceinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
-	d3dukmdt.h
api_name:
-	D3DDDI_SURFACEINFO
product: Windows
targetos: Windows
req.typenames: D3DDDI_SURFACEINFO
---

# _D3DDDI_SURFACEINFO structure


## -description


The D3DDDI_SURFACEINFO structure describes a resource type, such as a surface.


## -syntax


````
typedef struct _D3DDDI_SURFACEINFO {
  UINT       Width;
  UINT       Height;
  UINT       Depth;
  const VOID *pSysMem;
  UINT       SysMemPitch;
  UINT       SysMemSlicePitch;
} D3DDDI_SURFACEINFO;
````


## -struct-fields




### -field Width

[in] The width, in pixels, of the surface or volume or the length, in pixels, of the linear resource.


### -field Height

[in] The height, in pixels, of the surface or volume.


### -field Depth

[in] The depth, in pixels, of the volume.


### -field pSysMem

[in] A pointer to a buffer that contains the contents of the resource if the resource exists in system memory and <b>NULL</b> if the resource exists in video memory.

Note that this member is valid only if the <b>Pool</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> structure for creating the resource is set to the D3DDDIPOOL_SYSTEMMEM value.


### -field SysMemPitch

[in] The pitch, in bytes, of the surface--that is, the distance, in bytes, to the start of the next line.


### -field SysMemSlicePitch

[in] The slice, in bytes, of the volume.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_SURFACEINFO structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

