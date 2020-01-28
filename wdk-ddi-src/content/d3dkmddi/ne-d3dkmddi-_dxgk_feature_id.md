---
UID: NE:d3dkmddi._DXGK_FEATURE_ID
title: _DXGK_FEATURE_ID
author: windows-driver-content
description: The feature ID of a driver feature.
tech.root: display
ms.assetid: ff693135-419c-4950-a780-f99313dd5ea5
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.keywords: _DXGK_FEATURE_ID, DXGK_FEATURE_ID,
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: DXGK_FEATURE_ID
targetos: Windows
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
f1_keywords:
 - "d3dkmddi/_DXGK_FEATURE_ID"
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_FEATURE_ID
product:
 - Windows
dev_langs:
 - c++
---

# _DXGK_FEATURE_ID enumeration

## -description

The feature ID of a driver feature.

## -enum-fields

### -field DXGK_FEATURE_HWSCH

Represents a hardware scheduling feature id.

## -remarks

For each feature in this enumeration, if the driver supports it, the driver must call the OS to query its enabled status, and only enable the feature if the OS returned `Enabled=TRUE`. Drivers that don't support the feature doesn't have to call the OS to query its status.

## -see-also

