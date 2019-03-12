---
UID: NS:d3dkmddi._DXGK_WDDMDEVICECAPS
title: DXGK_WDDMDEVICECAPS
author: windows-driver-content
description: 
tech.root: display
ms.assetid: 4c784d95-46ae-4e6e-89d6-0db4738a5cfd
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.keywords: DXGK_WDDMDEVICECAPS, DXGK_WDDMDEVICECAPS, 
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
req.typenames: DXGK_WDDMDEVICECAPS
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3dkmddi.h
api_name: 
 - DXGK_WDDMDEVICECAPS
product:
- Windows
targetos: Windows
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6
---

# DXGK_WDDMDEVICECAPS structure

## -description

Windows Display Driver Model device capabilities.

These caps must be filled out by the kernel mode driver in response to **DXGKQAITYPE_WDDMDEVICECAPS** QueryAdapterInfo request. These are queried by the OS during device initialization after DxgkDdiAddDevice returns and before DxgkDdiStartDevice is called.

## -struct-fields

### -field WDDMVersion
 
The WDDM version.

## -remarks

## -see-also