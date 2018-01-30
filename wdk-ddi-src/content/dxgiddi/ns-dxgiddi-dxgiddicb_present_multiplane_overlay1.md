---
UID: NS:dxgiddi.DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1
title: DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1
author: windows-driver-content
description: Describes multiplane overlay allocations, private driver data, and context information for each multiplane overlay plane.
old-location: display\dxgiddicb_present_multiplane_overlay1.htm
old-project: display
ms.assetid: AA716307-C235-47B2-BEB6-586FD6013280
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1, dxgiddi/DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1, DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1 structure [Display Devices], display.dxgiddicb_present_multiplane_overlay1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
-	dxgiddi.h
apiname:
-	DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1
product: Windows
targetos: Windows
req.typenames: DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1
---

# DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1 structure


## -description


Describes multiplane overlay allocations, private driver data, and context information for each multiplane overlay plane. 


## -syntax


````
typedef struct _DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1 {
  VOID                                  *pDXGIContext;
  DWORD                                 PresentPlaneCount;
  DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO **ppPresentPlanes;
} DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1;
````


## -struct-fields




### -field pDXGIContext

A handle to the DXGI context. This handle is opaque to the driver. The driver should assign the handle from the pDXGIContext member DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY1 structure that the driver received in a call to its pfnPresentMultiplaneOverlay function to this member.


### -field PresentPlaneCount

The number of planes in the array that the ppPresentPlanes member specifies.


### -field ppPresentPlanes

An array of pointers to a structure of type DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO that specify information about the multiplane overlay planes.

