---
UID: NS:d3dkmddi._DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2
title: "_DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2"
author: windows-driver-content
description: DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 is passed to the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 function to change the overlay configuration being displayed.DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 is passed to the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 function to change the overlay configuration being displayed.
old-location: display\dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay2.htm
old-project: display
ms.assetid: 6138BAF5-F953-47E7-A572-BE4673CF7046
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay2, _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2, DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2, d3dkmddi/DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2, DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 structure [Display Devices]
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
-	DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2
product: Windows
targetos: Windows
req.typenames: DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2
---

# _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 structure


## -description



<b>DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2</b> is passed to the  <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay2.md">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2</a> function to change the overlay configuration being displayed.




## -syntax


````
typedef struct _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 {
  UINT                             ContextCount;
  HANDLE                           Context[1+D3DDDI_MAX_BROADCAST_CONTEXT];
  DXGK_SETVIDPNSOURCEADDRESS_FLAGS Flags;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID   VidPnSourceId;
  UINT                             PlaneCount;
  DXGK_MULTIPLANE_OVERLAY_PLANE2   pPlanes;
  UINT                             Duration;
} DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2;
````


## -struct-fields




### -field ContextCount

The number of contexts in the array that the <b>Context</b> member specifies.


### -field Context

An array of handles to the contexts that contributed to a display operation.


### -field Flags

A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_setvidpnsourceaddress_flags.md">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a> structure that identifies the type of display operation to perform.


### -field VidPnSourceId

An integer that identifies a video present source on the display adapter.


### -field PlaneCount

The number of overlay planes in the <b>pPlanes</b> list.


### -field pPlanes

An array of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_plane2.md">DXGK_MULTIPLANE_OVERLAY_PLANE2</a> structures that specify the overlay planes to display.


### -field Duration

The length of time, in 100 nanoseconds units, between when the current present operation flips to the screen and the next vertical blanking interrupt occurs.

If zero, the refresh rate should be the default rate based on the current mode.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_setvidpnsourceaddress_flags.md">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay2.md">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_plane2.md">DXGK_MULTIPLANE_OVERLAY_PLANE2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

