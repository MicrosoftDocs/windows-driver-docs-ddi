---
UID: NS:dispmprt._DXGK_INTEGRATED_DISPLAY_CHILD
title: DXGK_INTEGRATED_DISPLAY_CHILD (dispmprt.h)
description: Learn more about the _DXGK_INTEGRATED_DISPLAY_CHILD structure.
tech.root: display
ms.date: 01/13/2025
req.header: dispmprt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
req.typenames: DXGK_INTEGRATED_DISPLAY_CHILD, *PDXGK_INTEGRATED_DISPLAY_CHILD
f1_keywords:
 - _DXGK_INTEGRATED_DISPLAY_CHILD
 - dispmprt/_DXGK_INTEGRATED_DISPLAY_CHILD
 - PDXGK_INTEGRATED_DISPLAY_CHILD
 - dispmprt/PDXGK_INTEGRATED_DISPLAY_CHILD
 - DXGK_INTEGRATED_DISPLAY_CHILD
 - dispmprt/DXGK_INTEGRATED_DISPLAY_CHILD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_INTEGRATED_DISPLAY_CHILD
 - PDXGK_INTEGRATED_DISPLAY_CHILD
 - DXGK_INTEGRATED_DISPLAY_CHILD
---

# DXGK_INTEGRATED_DISPLAY_CHILD structure

## -description

The **DXGK_INTEGRATED_DISPLAY_CHILD** structure provides information about the connected integrated display.

## -struct-fields

### -field InterfaceTechnology

Provides the type of connection used for the integrated display.  Typically, **InterfaceTechnology** would be one of the inherently internal display types:

* D3DKMDT_VOT_INTERNAL
* D3DKMDT_VOT_LVDS
* D3DKMDT_VOT_DISPLAYPORT_EMBEDDED
* D3DKMDT_VOT_UDI_EMBEDDED

However, since it's common to use external connector types to connect integrated displays in larger form factor systems with a built-in display such as all-in-one systems, the following digital connection types are also allowed:

* D3DKMDT_VOT_DVI
* D3DKMDT_VOT_HDMI
* D3DKMDT_VOT_D_JPN
* D3DKMDT_VOT_SDI
* D3DKMDT_VOT_DISPLAYPORT_EXTERNAL
* D3DKMDT_VOT_UDI_EXTERNAL

### -field DescriptorLength

The size in bytes of the descriptor in the **Descriptor** field of the [**DXGK_QUERYINTEGRATEDDISPLAYOUT**](../d3dkmddi/ns-d3dkmddi-dxgk_queryintegrateddisplayout.md) structure.

## -see-also

[**DXGK_CHILD_CAPABILITIES**](ns-dispmprt-_dxgk_child_capabilities.md)

[**DXGK_QUERYINTEGRATEDDISPLAYOUT**](../d3dkmddi/ns-d3dkmddi-dxgk_queryintegrateddisplayout.md)
