---
UID: NS:d3d10umddi.D3D10DDI_MIPINFO
title: D3D10DDI_MIPINFO
author: windows-driver-content
description: The D3D10DDI_MIPINFO structure describes the MIP-level texture and physical coordinates of a surface.
old-location: display\d3d10ddi_mipinfo.htm
old-project: display
ms.assetid: 5f00ff32-5ecf-40ca-91bb-aacc542bb7f4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3D10DDI_MIPINFO, UMDisplayDriver_Dx10param_Structs_67768e5f-a18d-4bd9-a1be-96587f267c36.xml, D3D10DDI_MIPINFO structure [Display Devices], D3D10DDI_MIPINFO, display.d3d10ddi_mipinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
apiname:
-	D3D10DDI_MIPINFO
product: Windows
targetos: Windows
req.typenames: D3D10DDI_MIPINFO
---

# D3D10DDI_MIPINFO structure


## -description


The D3D10DDI_MIPINFO structure describes the MIP-level texture and physical coordinates of a surface.


## -syntax


````
typedef struct D3D10DDI_MIPINFO {
  UINT TexelWidth;
  UINT TexelHeight;
  UINT TexelDepth;
  UINT PhysicalWidth;
  UINT PhysicalHeight;
  UINT PhysicalDepth;
} D3D10DDI_MIPINFO;
````


## -struct-fields




### -field TexelWidth

[in] The width, in texels, of the surface or volume, or the length, in texels, of the linear resource.


### -field TexelHeight

[in] The height, in texels, of the surface or volume.


### -field TexelDepth

[in] The depth, in texels, of the volume.


### -field PhysicalWidth

[in] The width, in pixels, of the surface or volume, or the length, in pixels, of the linear resource.


### -field PhysicalHeight

[in] The height, in pixels, of the surface or volume.


### -field PhysicalDepth

[in] The depth, in pixels, of the volume.


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDI_MIPINFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

