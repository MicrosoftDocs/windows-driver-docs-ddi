---
UID: NS:d3d12umddi.D3D12DDIARG_OFFERRESOURCES
title: D3D12DDIARG_OFFERRESOURCES
author: windows-driver-content
description: Describes video memory resources that the user-mode display driver offers for reuse.
tech.root: display
ms.assetid: 4b7b2415-7ecb-4711-87cc-e309fac479c0
ms.author: windowsdriverdev
ms.date: 04/04/2019
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_OFFERRESOURCES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDIARG_OFFERRESOURCES, D3D12DDIARG_OFFERRESOURCES, 
req.header: d3d12umddi.h
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
req.typenames: D3D12DDIARG_OFFERRESOURCES
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDIARG_OFFERRESOURCES
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# D3D12DDIARG_OFFERRESOURCES structure

## -description

Describes video memory resources that the user-mode display driver offers for reuse.

## -struct-fields

### -field NumObjects

The number of elements in the array pointed to by *pObjects*.

### -field pObjects

A pointer to an array of handles to the video memory objects that the driver offers.

### -field Priority

A value of type [D3DDDI_OFFER_PRIORITY](../d3dukmdt/ne-d3dukmdt-_d3dddi_offer_priority.md) that indicates the importance of the resources pointed to by *pObjects*.

### -field Reserved

Reserved.

## -remarks

## -see-also
