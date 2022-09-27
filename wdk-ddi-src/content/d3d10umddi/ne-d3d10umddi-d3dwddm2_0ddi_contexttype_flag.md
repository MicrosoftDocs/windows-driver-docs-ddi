---
UID: NE:d3d10umddi.D3DWDDM2_0DDI_CONTEXTTYPE_FLAG
title: D3DWDDM2_0DDI_CONTEXTTYPE_FLAG (d3d10umddi.h)
description: D3DWDDM2_0DDI_CONTEXTTYPE_FLAG describes the type of context being created for interacting with JPEG hardware.
old-location: display\d3dwddm2_0ddi_contexttype_flag.htm
ms.date: 08/22/2022
keywords: ["D3DWDDM2_0DDI_CONTEXTTYPE_FLAG enumeration"]
ms.keywords: D3DWDDM2_0DDI_CONTEXTTYPE_3D, D3DWDDM2_0DDI_CONTEXTTYPE_ALL, D3DWDDM2_0DDI_CONTEXTTYPE_COMPUTE, D3DWDDM2_0DDI_CONTEXTTYPE_COPY, D3DWDDM2_0DDI_CONTEXTTYPE_FLAG, D3DWDDM2_0DDI_CONTEXTTYPE_FLAG enumeration [Display Devices], D3DWDDM2_0DDI_CONTEXTTYPE_IMAGE, D3DWDDM2_0DDI_CONTEXTTYPE_VIDEO, d3d10umddi/D3DWDDM2_0DDI_CONTEXTTYPE_3D, d3d10umddi/D3DWDDM2_0DDI_CONTEXTTYPE_ALL, d3d10umddi/D3DWDDM2_0DDI_CONTEXTTYPE_COMPUTE, d3d10umddi/D3DWDDM2_0DDI_CONTEXTTYPE_COPY, d3d10umddi/D3DWDDM2_0DDI_CONTEXTTYPE_FLAG, d3d10umddi/D3DWDDM2_0DDI_CONTEXTTYPE_IMAGE, d3d10umddi/D3DWDDM2_0DDI_CONTEXTTYPE_VIDEO, display.d3dwddm2_0ddi_contexttype_flag
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3DWDDM2_0DDI_CONTEXTTYPE_FLAG
f1_keywords:
 - D3DWDDM2_0DDI_CONTEXTTYPE_FLAG
 - d3d10umddi/D3DWDDM2_0DDI_CONTEXTTYPE_FLAG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3DWDDM2_0DDI_CONTEXTTYPE_FLAG
---

# D3DWDDM2_0DDI_CONTEXTTYPE_FLAG enumeration

## -description

**D3DWDDM2_0DDI_CONTEXTTYPE_FLAG** describes the type of context being created for interacting with JPEG hardware.

## -enum-fields

### -field D3DWDDM2_0DDI_CONTEXTTYPE_ALL:0x00000000

Indicates that all JPEG contexts should be created.

### -field D3DWDDM2_0DDI_CONTEXTTYPE_3D:0x00000001

Indicates that a JPEG 3D context should be created.

### -field D3DWDDM2_0DDI_CONTEXTTYPE_COMPUTE:0x00000002

Indicates that a JPEG compute context should be created.

### -field D3DWDDM2_0DDI_CONTEXTTYPE_COPY:0x00000004

Indicates that  a JPEG copy context should be created.

### -field D3DWDDM2_0DDI_CONTEXTTYPE_VIDEO:0x00000008

Indicates that a JPEG video context should be created.
