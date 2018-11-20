---
UID: NS:d3d12umddi.D3D12DDI_EXISTING_COLLECTION_DESC_0054
title: D3D12DDI_EXISTING_COLLECTION_DESC_0054
author: windows-driver-content
description: An existing collection.
ms.assetid: d9974a90-8c8b-4fd8-8e82-5938d3c97590
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDI_EXISTING_COLLECTION_DESC_0054, D3D12DDI_EXISTING_COLLECTION_DESC_0054, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_EXISTING_COLLECTION_DESC_0054
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_EXISTING_COLLECTION_DESC_0054
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_EXISTING_COLLECTION_DESC_0054 structure

## -description

An existing collection. A collection is a state object type that contains any amount of subobjects, but doesn't have constraints.

## -struct-fields

### -field hExistingCollection

A handle to an existing collection.

### -field NumExports

The number of [D3D12DDI_EXPORT_DESC_0054](ns-d3d12umddi-d3d12ddi_export_desc_0054.md) structures that pExports points to.

### -field pExports
 
Pointer to an array of D3D12DDI_EXPORT_DESC_0054 structures.

## -remarks

The purpose of a collection is to allow an application to pass an arbitrarily large or small collection of state to drivers to compile at once.

## -see-also
