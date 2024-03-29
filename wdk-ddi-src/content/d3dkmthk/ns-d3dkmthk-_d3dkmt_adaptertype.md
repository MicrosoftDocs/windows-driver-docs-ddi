---
UID: NS:d3dkmthk._D3DKMT_ADAPTERTYPE
title: _D3DKMT_ADAPTERTYPE (d3dkmthk.h)
description: Specifies the type of display device that the graphics adapter supports.
old-location: display\d3dkmt_adaptertype.htm
ms.date: 03/08/2022
keywords: ["D3DKMT_ADAPTERTYPE structure"]
ms.keywords: D3DKMT_ADAPTERTYPE, D3DKMT_ADAPTERTYPE structure [Display Devices], _D3DKMT_ADAPTERTYPE, d3dkmthk/D3DKMT_ADAPTERTYPE, display.d3dkmt_adaptertype
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
tech.root: display
req.typenames: D3DKMT_ADAPTERTYPE
f1_keywords:
 - _D3DKMT_ADAPTERTYPE
 - d3dkmthk/_D3DKMT_ADAPTERTYPE
 - D3DKMT_ADAPTERTYPE
 - d3dkmthk/D3DKMT_ADAPTERTYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - _D3DKMT_ADAPTERTYPE
 - D3DKMT_ADAPTERTYPE
---

# _D3DKMT_ADAPTERTYPE structure

## -description

Specifies the type of display device that the graphics adapter supports.

## -struct-fields

### -field RenderSupported

The adapter supports a render device.

### -field DisplaySupported

The adapter supports a display device.

### -field SoftwareDevice

The adapter supports a non-plug and play (PnP) device that is implemented in software.

### -field PostDevice

The adapter supports a power-on self-test (POST) device.

### -field HybridDiscrete

The adapter supports a hybrid discrete device.

### -field HybridIntegrated

The adapter supports a hybrid integrated device.

### -field IndirectDisplayDevice

The adapter supports an indirect display device.

### -field Paravirtualized

The adapter supports para-virtualization.

### -field ACGSupported

The adapter supports Arbitrary Code Guard (ACG).

### -field SupportSetTimingsFromVidPn

### -field Detachable

The adapter supports a detachable device.

### -field ComputeOnly

The adapter supports a compute-only device.

### -field Prototype

The adapter supports a prototype device.

### -field RuntimePowerManagement

The adapter supports a runtime power management device.

### -field Reserved

Reserved for internal use.

### -field Value

The value used to operate over the other members.
