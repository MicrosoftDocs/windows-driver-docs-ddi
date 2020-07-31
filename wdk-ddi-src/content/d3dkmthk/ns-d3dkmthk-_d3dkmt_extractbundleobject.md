---
UID: NS:d3dkmthk._D3DKMT_EXTRACTBUNDLEOBJECT
title: _D3DKMT_EXTRACTBUNDLEOBJECT (d3dkmthk.h)
description: Used to extract the bundle object.
old-location: display\d3dkmt-extractbundleobject.htm
ms.assetid: 85112ddb-47e6-4874-bd64-a7e4d7ca0fd3
ms.date: 05/10/2018
keywords: ["_D3DKMT_EXTRACTBUNDLEOBJECT structure"]
ms.keywords: D3DKMT_EXTRACTBUNDLEOBJECT, D3DKMT_EXTRACTBUNDLEOBJECT structure [Display Devices], _D3DKMT_EXTRACTBUNDLEOBJECT, d3dkmthk/D3DKMT_EXTRACTBUNDLEOBJECT, display.d3dkmt-extractbundleobject
f1_keywords:
 - "d3dkmthk/D3DKMT_EXTRACTBUNDLEOBJECT"
 - "D3DKMT_EXTRACTBUNDLEOBJECT"
req.header: d3dkmthk.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Windows 10, version 1709
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_EXTRACTBUNDLEOBJECT
targetos: Windows
tech.root: display
req.typenames: D3DKMT_EXTRACTBUNDLEOBJECT
---

# _D3DKMT_EXTRACTBUNDLEOBJECT structure


## -description


Used to extract the bundle object.


## -struct-fields




### -field hNtBundleHandle

The NT bundle handle.


### -field cObjects

The number of the DXGK object to be unbundled.


### -field pdwDesiredAccess

The desired access for each NT handle for DXGK objects.


### -field phNtHandles

The pointer to an array of NT handles for each DXGK object.

