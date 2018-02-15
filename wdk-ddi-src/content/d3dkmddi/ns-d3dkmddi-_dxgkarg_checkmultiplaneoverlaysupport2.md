---
UID: NS:d3dkmddi._DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2
title: "_DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2"
author: windows-driver-content
description: DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2 is passed to the DxgkDdiCheckMultiPlaneOverlaySupport2 function to determine whether a specific multi-plane overlay configuration is supported.
old-location: display\dxgkarg_checkmultiplaneoverlaysupport2.htm
old-project: display
ms.assetid: 477EBC8A-04A5-4904-AC62-0FA7DB861ACC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2, *IN_OUT_PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2, d3dkmddi/DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2, _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2, display.dxgkarg_checkmultiplaneoverlaysupport2, DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2 structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2
product: Windows
targetos: Windows
req.typenames: DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2
---

# _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2 structure


## -description


<b>DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2</b> is passed to the  <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport2.md">DxgkDdiCheckMultiPlaneOverlaySupport2</a> function to determine whether a specific multi-plane overlay configuration is supported. 


## -syntax


````
typedef struct _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2 {
  UINT                                              PlaneCount;
  DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE*        pPlanes;
  BOOL                                              Supported;
  DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO ReturnInfo;
} DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2;
````


## -struct-fields




### -field PlaneCount

The number of planes to be enabled.


### -field pPlanes

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_plane_with_source.md">DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE</a> 
                                                                        structure that specifies support attributes that the hardware
                                                                        provides for multi-plane overlays.


### -field Supported

<b>TRUE</b> if the multi-plane overlay configuration can be supported, otherwise <b>FALSE</b>.


### -field ReturnInfo

Specifies additional information.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport2.md">DxgkDdiCheckMultiPlaneOverlaySupport2</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_plane_with_source.md">DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

