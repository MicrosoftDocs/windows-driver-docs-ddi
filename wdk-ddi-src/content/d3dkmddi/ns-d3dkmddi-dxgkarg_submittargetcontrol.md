---
UID: NS:d3dkmddi._DXGKARG_SUBMITTARGETCONTROL
title: DXGKARG_SUBMITTARGETCONTROL
author: windows-driver-content
description: Arguments used the by the DXGKDDI_SUBMITTARGETCONTROL callback function to request control operations to be performed on a target.
tech.root: display
ms.assetid: c5a946d3-1e58-4705-bde0-0d4e2ce9e7a6
ms.author: windowsdriverdev
ms.date: 08/19/2019
keywords: ["DXGKARG_SUBMITTARGETCONTROL structure"]
f1_keywords:
 - "d3dkmddi/DXGKARG_SUBMITTARGETCONTROL"
ms.keywords: DXGKARG_SUBMITTARGETCONTROL, DXGKARG_SUBMITTARGETCONTROL, *PDXGKARG_SUBMITTARGETCONTROL, *IN_OUT_PDXGKARG_SUBMITTARGETCONTROL
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARG_SUBMITTARGETCONTROL, *PDXGKARG_SUBMITTARGETCONTROL
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3dkmddi.h
api_name: 
 - DXGKARG_SUBMITTARGETCONTROL
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: WDDM 2.6, 19H1
---

# DXGKARG_SUBMITTARGETCONTROL structure

## -description

Arguments used the by the [DXGKDDI_SUBMITTARGETCONTROL](nc-d3dkmddi-dxgkddi_submittargetcontrol.md) callback function to request control operations to be performed on a target.

## -struct-fields

### -field TargetId

[in] The target to be modified.

### -field Type

[in] The target control type.

### -field pDsi2Transmission
 
[in, out] A pointer to a [DXGK_DSI2_TRANSMISSION](ns-d3dkmddi-dxgk_dsi2_transmission.md) that represents the Dsi2 transmission.

## -remarks

## -see-also
