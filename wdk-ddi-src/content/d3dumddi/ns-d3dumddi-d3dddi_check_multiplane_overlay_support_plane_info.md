---
UID: NS:d3dumddi.D3DDDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO
title: D3DDDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO (d3dumddi.h)
description: Used to check multiplane overlay support plane info.
ms.assetid: 4dc51026-e8e3-4950-a4b5-194132c1749b
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO"
ms.keywords: D3DDDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO, D3DDDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO, 
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type:
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DDDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dumddi.h
api_name: 
- D3DDDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# D3DDDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO structure

## -description

Used to check multiplane overlay support plane info.

## -struct-fields

### -field hResource

A handle to the resource. The display miniport driver must set this member to a value that it can use to refer to its private tracking structure for the resource.

### -field SubResourceIndex

The zero-based index into the resource, which is specified by the handle in the **hResource** member. This index indicates the subresource, or surface, on which an overlay plane is to be displayed.

### -field PlaneAttributes
 
A [D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES](ns-d3dumddi-_d3dddi_multiplane_overlay_attributes.md) structure that specifies overlay plane attributes.

## -remarks

## -see-also
