---
UID: NS:dxgiddi.DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO
title: DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO (dxgiddi.h)
description: Specifies the support attributes that the hardware provides for multiplane overlays.
old-location: display\dxgi_ddi_check_multiplaneoverlaysupport_plane_info.htm
tech.root: display
ms.assetid: 3a1e41b5-cd62-436b-a4ed-6dee99c03cac
ms.date: 05/10/2018
ms.keywords: DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO, DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO structure [Display Devices], DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO, DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO structure [Display Devices], display.dxgi_ddi_check_multiplaneoverlaysupport_plane_info, dxgiddi/DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	Dxgiddi.h
api_name:
-	DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO
---

# DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO structure


## -description


Specifies the support attributes that the hardware provides for multiplane overlays.


## -struct-fields




### -field hResource

A handle to the resource. The display miniport driver must set this member to a value that it can use to refer to its private tracking structure for the resource.


### -field SubResourceIndex

The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource, or surface, on which an overlay plane is to be displayed.


### -field PlaneAttributes

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh780283">DXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES</a> structure that specifies overlay plane attributes.

