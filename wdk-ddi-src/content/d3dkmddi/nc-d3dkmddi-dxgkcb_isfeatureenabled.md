---
UID: NC:d3dkmddi.DXGKCB_ISFEATUREENABLED
title: DXGKCB_ISFEATUREENABLED
description: Queries for the enabled state of the feature.
tech.root: display
ms.assetid: c16b0f26-67e7-4048-8f47-2815d87a823e
ms.date: 04/04/2019
keywords: ["DXGKCB_ISFEATUREENABLED callback function"]
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
f1_keywords:
 - DXGKCB_ISFEATUREENABLED
 - d3dkmddi/DXGKCB_ISFEATUREENABLED
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_ISFEATUREENABLED
product:
 - Windows
dev_langs:
 - c++
---

# DXGKCB_ISFEATUREENABLED callback function


## -description

Queries for the enabled state of the feature.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -prototype

```
//Declaration

DXGKCB_ISFEATUREENABLED DxgkcbIsfeatureenabled; 

// Definition

NTSTATUS DxgkcbIsfeatureenabled 
(
)
{...}

```

## -remarks

## -see-also

