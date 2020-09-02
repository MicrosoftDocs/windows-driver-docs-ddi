---
UID: NE:d3d10umddi.D3DWDDM2_6DDI_SCANOUT_FLAGS
title: D3DWDDM2_6DDI_SCANOUT_FLAGS
author: windows-driver-content
description: Indicates the transformation requirement in preparation for a flip operation.
tech.root: display
ms.assetid: 540df0eb-85df-4793-b70a-4035a32cf716
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["D3DWDDM2_6DDI_SCANOUT_FLAGS enumeration"]
ms.keywords: D3DWDDM2_6DDI_SCANOUT_FLAGS, D3DWDDM2_6DDI_SCANOUT_FLAGS,
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d10umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3DWDDM2_6DDI_SCANOUT_FLAGS
targetos: Windows
ms.custom: WDDM 2.6, 19H1
f1_keywords:
 - D3DWDDM2_6DDI_SCANOUT_FLAGS
 - d3d10umddi/D3DWDDM2_6DDI_SCANOUT_FLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3DWDDM2_6DDI_SCANOUT_FLAGS
product:
 - Windows
---

# D3DWDDM2_6DDI_SCANOUT_FLAGS enumeration


## -description

Used in the [PFND3DWDDM2_6DDI_QUERY_SCANOUT_CAPS](nc-d3d10umddi-pfnd3dwddm2_6ddi_query_scanout_caps.md) callback to indicate the transformation requirement in preparation for a flip operation.

## -enum-fields

### -field D3DWDDM2_6DDI_SCANOUT_FLAG_NONE

A transformation requirement is not defined.

### -field D3DWDDM2_6DDI_SCANOUT_FLAG_TRANSFORMATION_REQUIRED

A transformation is required. If transformation is required, the runtime will call [PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION](nc-d3d10umddi-pfnd3dwddm2_6ddi_prepare_scanout_transformation.md).

### -field D3DWDDM2_6DDI_SCANOUT_FLAG_TRANSFORMATION_DESIRED

A transformation should occur. If there has been no API request to disable the transformation, then the runtime will call [PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION](nc-d3d10umddi-pfnd3dwddm2_6ddi_prepare_scanout_transformation.md).

### -field D3DWDDM2_6DDI_SCANOUT_FLAG_UNPREDICTABLE_TIMING

Indicates to the runtime whether the resulting allocation follows a predictable scanout timing or not. This information will be used to adjust the front-buffer rendering safety margins.

## -remarks

The driver may not set both the D3DWDDM2_6DDI_SCANOUT_FLAG_TRANSFORMATION_REQUIRED and D3DWDDM2_6DDI_SCANOUT_FLAG_TRANSFORMATION_DESIRED flag.

## -see-also

[PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION](nc-d3d10umddi-pfnd3dwddm2_6ddi_prepare_scanout_transformation.md)

[PFND3DWDDM2_6DDI_QUERY_SCANOUT_CAPS](nc-d3d10umddi-pfnd3dwddm2_6ddi_query_scanout_caps.md)

