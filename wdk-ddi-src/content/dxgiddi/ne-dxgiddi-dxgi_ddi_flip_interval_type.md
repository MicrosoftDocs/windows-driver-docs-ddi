---
UID: NE:dxgiddi.DXGI_DDI_FLIP_INTERVAL_TYPE
title: DXGI_DDI_FLIP_INTERVAL_TYPE (dxgiddi.h)
description: The DXGI_DDI_FLIP_INTERVAL_TYPE enumeration type contains values that identify the type of flip that occurs in present operations.
old-location: display\dxgi_ddi_flip_interval_type.htm
tech.root: display
ms.assetid: e33da768-9d57-4b07-9c4e-c86d19828291
ms.date: 05/10/2018
keywords: ["DXGI_DDI_FLIP_INTERVAL_TYPE enumeration"]
ms.keywords: DXGI_DDI_FLIP_INTERVAL_FOUR, DXGI_DDI_FLIP_INTERVAL_IMMEDIATE, DXGI_DDI_FLIP_INTERVAL_ONE, DXGI_DDI_FLIP_INTERVAL_THREE, DXGI_DDI_FLIP_INTERVAL_TWO, DXGI_DDI_FLIP_INTERVAL_TYPE, DXGI_DDI_FLIP_INTERVAL_TYPE enumeration [Display Devices], UMDisplayDriver_Dx10param_Structs_65a96d1c-4c37-4fdd-b79e-2a90559db67d.xml, display.dxgi_ddi_flip_interval_type, dxgiddi/DXGI_DDI_FLIP_INTERVAL_FOUR, dxgiddi/DXGI_DDI_FLIP_INTERVAL_IMMEDIATE, dxgiddi/DXGI_DDI_FLIP_INTERVAL_ONE, dxgiddi/DXGI_DDI_FLIP_INTERVAL_THREE, dxgiddi/DXGI_DDI_FLIP_INTERVAL_TWO, dxgiddi/DXGI_DDI_FLIP_INTERVAL_TYPE
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: DXGI_DDI_FLIP_INTERVAL_TYPE
f1_keywords:
 - DXGI_DDI_FLIP_INTERVAL_TYPE
 - dxgiddi/DXGI_DDI_FLIP_INTERVAL_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxgiddi.h
api_name:
 - DXGI_DDI_FLIP_INTERVAL_TYPE
---

# DXGI_DDI_FLIP_INTERVAL_TYPE enumeration


## -description

The DXGI_DDI_FLIP_INTERVAL_TYPE enumeration type contains values that identify the type of flip that occurs in present operations.

## -enum-fields

### -field DXGI_DDI_FLIP_INTERVAL_IMMEDIATE

Indicates to perform the flip immediately without waiting for a vertical sync to occur.

### -field DXGI_DDI_FLIP_INTERVAL_ONE

Indicates to perform the flip on every vertical sync.

### -field DXGI_DDI_FLIP_INTERVAL_TWO

Indicates to perform the flip on every other vertical sync.

### -field DXGI_DDI_FLIP_INTERVAL_THREE

Indicates to perform the flip on every third vertical sync.

### -field DXGI_DDI_FLIP_INTERVAL_FOUR

Indicates to perform the flip on every fourth vertical sync.

### -field DXGI_DDI_FLIP_INTERVAL_IMMEDIATE_ALLOW_TEARING

## -see-also

<a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_present">DXGI_DDI_ARG_PRESENT</a>