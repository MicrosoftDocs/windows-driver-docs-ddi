---
UID: NS:d3dkmddi._DXGKARG_SETTARGETCONTENTTYPE
title: "_DXGKARG_SETTARGETCONTENTTYPE"
author: windows-driver-content
description: Used to hold the arguments for DXGKDDI_SETTARGETCONTENTTYPE.
old-location: display\dxgkarg_settargetcontenttype.htm
old-project: display
ms.assetid: BD849954-97CC-4314-B375-22829B0CEE86
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKARG_SETTARGETCONTENTTYPE, DXGKARG_SETTARGETCONTENTTYPE structure [Display Devices], PDXGKARG_SETTARGETCONTENTTYPE, PDXGKARG_SETTARGETCONTENTTYPE structure pointer [Display Devices], _DXGKARG_SETTARGETCONTENTTYPE, d3dkmddi/DXGKARG_SETTARGETCONTENTTYPE, d3dkmddi/PDXGKARG_SETTARGETCONTENTTYPE, display.dxgkarg_settargetcontenttype
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_SETTARGETCONTENTTYPE
product: Windows
targetos: Windows
req.typenames: DXGKARG_SETTARGETCONTENTTYPE
---

# _DXGKARG_SETTARGETCONTENTTYPE structure


## -description


Used to hold the arguments for <a href="https://msdn.microsoft.com/7639BF7B-6219-4490-953F-80E76CDFBAAA">DXGKDDI_SETTARGETCONTENTTYPE</a>



## -struct-fields




### -field TargetId

The identifier of a display adapter's video present target.


### -field ContentType

A D3DKMDT_VIDPN_PRESENT_PATH_CONTENT value indicating the type of content being presented on the target id for which the driver should optimize.

