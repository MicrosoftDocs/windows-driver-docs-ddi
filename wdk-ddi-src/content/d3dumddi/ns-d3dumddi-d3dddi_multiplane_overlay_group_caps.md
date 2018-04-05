---
UID: NS:d3dumddi.D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS
title: D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS
author: windows-driver-content
description: Used by the user-mode display driver to specify a group of overlay plane capabilities.
old-location: display\d3dddi_multiplane_overlay_group_caps.htm
old-project: display
ms.assetid: 6909579F-5387-4A35-B65B-EF77CC50DCC4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS, D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS structure [Display Devices], d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS, display.d3dddi_multiplane_overlay_group_caps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	D3dumddi.h
api_name:
-	D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS
---

# D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS structure


## -description


Used by the user-mode display driver to specify a group of overlay plane capabilities.


## -struct-fields




### -field NumPlanes

Specifies the number of overlay planes that are supported by the overlay planes within the capability group.


### -field MaxStretchFactor

Specifies the maximum stretch factor that is supported by the overlay planes within the capability group.

The stretch factor is the ratio of the final, stretched overlay plane size to the original size. For example, if the original overlay plane is 100 x 100 pixels, a value of 2.5 means that it can be stretched to 250 x 250 pixels.

It's not guaranteed that this stretch factor can be applied in all scenarios. For example, it might be possible to stretch only one overlay plane out of several using this factor.


### -field MaxShrinkFactor

Specifies the maximum shrink factor that is supported by the overlay planes within the capability group.

The shrink factor is the ratio of the final, shrunk overlay plane size to the original size. For example, if the original overlay plane is 100 x 100 pixels, a value of 0.25 means that it can be shrunk to 25 x 25 pixels.

It's not guaranteed that this shrink factor can be applied in all scenarios. For example, it might be possible to shrink only one overlay plane out of several using this factor.


### -field OverlayCaps

The overlay capabilities, given as a bitwise <b>OR</b> of values from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780237">D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS</a> enumeration.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780237">D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS</a>
 

 

