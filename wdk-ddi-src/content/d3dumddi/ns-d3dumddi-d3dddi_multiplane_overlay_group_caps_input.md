---
UID: NS:d3dumddi.D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT
title: D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT
author: windows-driver-content
description: Specifies info on a multiplane overlay capability group.
old-location: display\d3dddi_multiplane_overlay_group_caps_input.htm
tech.root: display
ms.assetid: 0AF66863-A1C0-4BCF-A677-BAF7F2961390
ms.date: 5/10/2018
ms.keywords: D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT, D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT structure [Display Devices], PD3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT, PD3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT structure pointer [Display Devices], d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT, d3dumddi/PD3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT, display.d3dddi_multiplane_overlay_group_caps_input
ms.topic: struct
req.header: d3dumddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT
---

# D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT structure


## -description


Specifies info on a multiplane overlay capability group.


## -struct-fields




### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input for which the capabilities are queried.


### -field GroupIndex

[in] The index of the overlay capability group for which capabilities are queried. This value is always between zero and (<a href="https://msdn.microsoft.com/library/windows/hardware/hh780236">D3DDDI_MULTIPLANE_OVERLAY_CAPS</a>.<b>NumCapabilityGroups</b> – 1).


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780236">D3DDDI_MULTIPLANE_OVERLAY_CAPS</a>
 

 

