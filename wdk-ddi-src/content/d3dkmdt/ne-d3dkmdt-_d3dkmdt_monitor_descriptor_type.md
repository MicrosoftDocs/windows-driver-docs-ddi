---
UID: NE:d3dkmdt._D3DKMDT_MONITOR_DESCRIPTOR_TYPE
title: "_D3DKMDT_MONITOR_DESCRIPTOR_TYPE"
author: windows-driver-content
description: The D3DKMDT_MONITOR_DESCRIPTOR_TYPE enumeration is used to indicate a particular type of monitor descriptor.
old-location: display\d3dkmdt_monitor_descriptor_type.htm
old-project: display
ms.assetid: f5ec761f-fc20-4baf-a012-c32356644a6c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMDT_MDT_OTHER, D3DKMDT_MDT_UNINITIALIZED, D3DKMDT_MDT_VESA_EDID_V1_BASEBLOCK, D3DKMDT_MDT_VESA_EDID_V1_BLOCKMAP, D3DKMDT_MONITOR_DESCRIPTOR_TYPE, D3DKMDT_MONITOR_DESCRIPTOR_TYPE enumeration [Display Devices], DmEnums_9d9ed4df-33cf-403a-96dd-c0745426daf1.xml, _D3DKMDT_MONITOR_DESCRIPTOR_TYPE, d3dkmdt/D3DKMDT_MDT_OTHER, d3dkmdt/D3DKMDT_MDT_UNINITIALIZED, d3dkmdt/D3DKMDT_MDT_VESA_EDID_V1_BASEBLOCK, d3dkmdt/D3DKMDT_MDT_VESA_EDID_V1_BLOCKMAP, d3dkmdt/D3DKMDT_MONITOR_DESCRIPTOR_TYPE, display.d3dkmdt_monitor_descriptor_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	D3DKMDT_MONITOR_DESCRIPTOR_TYPE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_MONITOR_DESCRIPTOR_TYPE
---

# _D3DKMDT_MONITOR_DESCRIPTOR_TYPE enumeration


## -description


The D3DKMDT_MONITOR_DESCRIPTOR_TYPE enumeration is used to indicate a particular type of monitor descriptor.


## -enum-fields




### -field D3DKMDT_MDT_UNINITIALIZED

Indicates that a variable of type D3DKMDT_MONITOR_DESCRIPTOR_TYPE has not yet been assigned a meaningful value.


### -field D3DKMDT_MDT_VESA_EDID_V1_BASEBLOCK

Indicates that the descriptor is an Extended Display Identification Data (EDID) base block.


### -field D3DKMDT_MDT_VESA_EDID_V1_BLOCKMAP

Indicates that the descriptor is an EDID block map.


### -field D3DKMDT_MDT_OTHER

Indicates that the descriptor has a type other than those indicated by the previous values of this enumeration.

