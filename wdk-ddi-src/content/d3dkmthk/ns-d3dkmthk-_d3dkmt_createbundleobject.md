---
UID: NS:d3dkmthk._D3DKMT_CREATEBUNDLEOBJECT
title: _D3DKMT_CREATEBUNDLEOBJECT (d3dkmthk.h)
description: Holds information to create a bundle object.
old-location: display\d3dkmt-createbundleobject.htm
ms.assetid: dbb01112-9d28-4dbf-88c7-3304d9d6a661
ms.date: 05/10/2018
ms.keywords: D3DKMT_CREATEBUNDLEOBJECT, D3DKMT_CREATEBUNDLEOBJECT structure [Display Devices], _D3DKMT_CREATEBUNDLEOBJECT, d3dkmthk/D3DKMT_CREATEBUNDLEOBJECT, display.d3dkmt-createbundleobject
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_CREATEBUNDLEOBJECT"
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
- D3DKMT_CREATEBUNDLEOBJECT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CREATEBUNDLEOBJECT
---

# _D3DKMT_CREATEBUNDLEOBJECT structure


## -description


Holds information to create a bundle object.


## -struct-fields




### -field cObjects

The number of the DXGK object to be bundled.


### -field phObjects

A pointer to the array of the DXGK object to be bundled.


### -field ppObjectAttributes

An array of pointers to object attributes for DXGK objects.


### -field pBundleObjectAttributes

Object attributes for the bundled object.


### -field dwBundleDesiredAccess

The desired access for bundle handle.


### -field hNtBundleHandle

The NT bundle handle.

