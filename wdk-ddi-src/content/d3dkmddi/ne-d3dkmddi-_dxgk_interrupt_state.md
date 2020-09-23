---
UID: NE:d3dkmddi._DXGK_INTERRUPT_STATE
title: _DXGK_INTERRUPT_STATE (d3dkmddi.h)
description: Provides additional information for DxgkDdi_ControlInterrupt2 or DxgkDdi_ControlInterrupt3 when VSYNC is not being utilized.
old-location: display\dxgk_interrupt_state.htm
ms.assetid: C72DF96B-5D12-4AC0-8FBB-904E087807DB
ms.date: 05/10/2018
keywords: ["DXGK_INTERRUPT_STATE enumeration"]
ms.keywords: DXGK_INTERRUPT_DISABLE, DXGK_INTERRUPT_ENABLE, DXGK_INTERRUPT_STATE, DXGK_INTERRUPT_STATE enumeration [Display Devices], _DXGK_INTERRUPT_STATE, d3dkmddi/DXGK_INTERRUPT_DISABLE, d3dkmddi/DXGK_INTERRUPT_ENABLE, d3dkmddi/DXGK_INTERRUPT_STATE, display.dxgk_interrupt_state
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10.
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
tech.root: display
req.typenames: DXGK_INTERRUPT_STATE
f1_keywords:
 - _DXGK_INTERRUPT_STATE
 - d3dkmddi/_DXGK_INTERRUPT_STATE
 - DXGK_INTERRUPT_STATE
 - d3dkmddi/DXGK_INTERRUPT_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_INTERRUPT_STATE
---

# _DXGK_INTERRUPT_STATE enumeration


## -description

Provides additional information for [*DxgkDdi_ControlInterrupt2*](./nc-d3dkmddi-dxgkddi_controlinterrupt2.md) or [**DxgkDdi_ControlInterrupt3**](./nc-d3dkmddi-dxgkddi_controlinterrupt3.md) when VSYNC is not being utilized.

> [!NOTE]
> This enumeration uses Enable as 0 and Disable as 1 in the bivalent state, which is the opposite of the Boolean value previously used in [*DxgkDdi_ControlInterrupt*](./nc-d3dkmddi-dxgkddi_controlinterrupt.md).

## -enum-fields

### -field DXGK_INTERRUPT_ENABLE

The interrupt is enabled.

### -field DXGK_INTERRUPT_DISABLE

The interrupt is disabled.