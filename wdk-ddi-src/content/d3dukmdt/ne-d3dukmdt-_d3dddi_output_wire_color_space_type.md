---
UID: NE:d3dukmdt._D3DDDI_OUTPUT_WIRE_COLOR_SPACE_TYPE
title: _D3DDDI_OUTPUT_WIRE_COLOR_SPACE_TYPE
author: windows-driver-content
description:
ms.assetid: 56328267-47fd-4d35-b033-34b5835a3802
ms.author: windowsdriverdev
ms.date:
ms.topic: enum
ms.keywords: _D3DDDI_OUTPUT_WIRE_COLOR_SPACE_TYPE, D3DDDI_OUTPUT_WIRE_COLOR_SPACE_TYPE,
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3dukmdt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3DDDI_OUTPUT_WIRE_COLOR_SPACE_TYPE
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dukmdt.h
apiname:
-	_D3DDDI_OUTPUT_WIRE_COLOR_SPACE_TYPE
product: 
- Windows
targetos: Windows
---

# _D3DDDI_OUTPUT_WIRE_COLOR_SPACE_TYPE enumeration

## -description

Specifies the final wire signaling colorspace values.

## -enum-fields

### -field D3DDDI_OUTPUT_WIRE_COLOR_SPACE_G22_P709

See [D3DDDI_COLOR_SPACE_TYPE](ne-d3dukmdt-d3dddi_color_space_type.md).

### -field D3DDDI_OUTPUT_WIRE_COLOR_SPACE_RESERVED

Reserved.

### -field D3DDDI_OUTPUT_WIRE_COLOR_SPACE_G2084_P2020

See [D3DDDI_COLOR_SPACE_TYPE](ne-d3dukmdt-d3dddi_color_space_type.md).

### -field D3DDDI_OUTPUT_WIRE_COLOR_SPACE_G22_P709_WCG

This enum value starts at 30, so as not to be confused with the existing [D3DDDI_COLOR_SPACE_TYPE](ne-d3dukmdt-d3dddi_color_space_type.md).
### -field D3DDDI_OUTPUT_WIRE_COLOR_SPACE_G22_P2020

Used by the OS only, graphics drivers should not expect this value.

### -field D3DDDI_OUTPUT_WIRE_COLOR_SPACE_G2084_P2020_HDR10PLUS

Used by the OS only, graphics drivers should not expect this value.

## -remarks

>[!NOTE]
> This enum is intended to specify the final wire signaling colorspace values. Do not mix it with the enum values defined in [D3DDDI_COLOR_SPACE_TYPE](ne-d3dukmdt-d3dddi_color_space_type.md), which are used to specify input colorspace for MPOs and other surfaces.

