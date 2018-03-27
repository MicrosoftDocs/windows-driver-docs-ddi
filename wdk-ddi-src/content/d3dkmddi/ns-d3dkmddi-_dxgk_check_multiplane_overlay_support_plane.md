---
UID: NS:d3dkmddi._DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
title: "_DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE"
author: windows-driver-content
description: Specifies the support attributes that the hardware provides for multiplane overlays.
old-location: display\dxgk_check_multiplane_overlay_support_plane.htm
old-project: display
ms.assetid: 28CC4BE1-D4C1-4D22-885B-D50BE5AD6EE6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE, DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE structure [Display Devices], _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE, d3dkmddi/DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE, display.dxgk_check_multiplane_overlay_support_plane
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
product: Windows
targetos: Windows
req.typenames: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
---

# _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE structure


## -description


Specifies the support attributes that the hardware provides for multiplane overlays.


## -struct-fields




### -field hAllocation

[out] A handle to the allocation. The display miniport driver must set this member to a value that it can use to refer to its private tracking structure for the allocation.


### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input for which the support levels are queried.


### -field PlaneAttributes

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh780301">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a> structure that specifies overlay plane attributes.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780301">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

