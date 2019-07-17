---
UID: NC:d3dkmddi.DXGKCB_ISFEATUREENABLED
title: DXGKCB_ISFEATUREENABLED
author: windows-driver-content
description: Queries for the enabled state of the feature.
tech.root: display
ms.assetid: c16b0f26-67e7-4048-8f47-2815d87a823e
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
f1_keywords:
 - "d3dkmddi/DXGKCB_ISFEATUREENABLED"
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
targetos: Windows
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
---

# DXGKCB_ISFEATUREENABLED callback function

## -description

Queries for the enabled state of the feature.

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

## -parameters


## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -remarks


## -see-also
