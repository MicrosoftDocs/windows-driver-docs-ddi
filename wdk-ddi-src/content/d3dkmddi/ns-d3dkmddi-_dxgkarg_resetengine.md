---
UID: NS:d3dkmddi._DXGKARG_RESETENGINE
title: DXGKARG_RESETENGINE (d3dkmddi.h)
description: Learn more about the _DXGKARG_RESETENGINE structure.
ms.date: 03/14/2024
keywords: ["DXGKARG_RESETENGINE structure"]
ms.keywords: "*INOUT_PDXGKARG_RESETENGINE, DXGKARG_RESETENGINE, DXGKARG_RESETENGINE structure [Display Devices], _DXGKARG_RESETENGINE, d3dkmddi/DXGKARG_RESETENGINE, display.dxgkarg_resetengine"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.typenames: DXGKARG_RESETENGINE
f1_keywords:
 - _DXGKARG_RESETENGINE
 - d3dkmddi/_DXGKARG_RESETENGINE
 - DXGKARG_RESETENGINE
 - d3dkmddi/DXGKARG_RESETENGINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - _DXGKARG_RESETENGINE
 - DXGKARG_RESETENGINE
---

# DXGKARG_RESETENGINE structure

## -description

The **DXGKARG_RESETENGINE** structure specifies a node within the physical display adapter that can be reset when the display port driver's GPU scheduler calls KMD's [**DxgkDdiResetEngine**](nc-d3dkmddi-dxgkddi_resetengine.md) function to request a node reset operation.

## -struct-fields

### -field NodeOrdinal [in]

The index of a node within the physical adapter that **EngineOrdinal** specifies that is being reset in a call to [**DxgkDdiResetEngine**](nc-d3dkmddi-dxgkddi_resetengine.md).

### -field EngineOrdinal [in]

The index that defines the physical adapter in a linked display adapter (LDA) configuration that the node specified by **NodeOrdinal** belongs to.

### -field LastAbortedFenceId [out]

The fence identifier for the last packet that was aborted in the middle of execution.

## -remarks

For more information, see [TDR changes in Windows 8](/windows-hardware/drivers/display/tdr-changes-in-windows-8).

## -see-also

[**DxgkDdiResetEngine**](nc-d3dkmddi-dxgkddi_resetengine.md)
