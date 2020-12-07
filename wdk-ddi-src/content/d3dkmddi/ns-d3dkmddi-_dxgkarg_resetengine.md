---
UID: NS:d3dkmddi._DXGKARG_RESETENGINE
title: _DXGKARG_RESETENGINE (d3dkmddi.h)
description: Specifies a node within the physical display adapter that can be reset when the display port driver's GPU scheduler calls the DxgkDdiResetEngine function to request a reset operation.
old-location: display\dxgkarg_resetengine.htm
ms.date: 05/10/2018
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
 - DXGKARG_RESETENGINE
---

# _DXGKARG_RESETENGINE structure


## -description

Specifies a node within the physical display adapter that can be reset when the display port driver's GPU scheduler calls the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_resetengine">DxgkDdiResetEngine</a> function to request a reset operation.

## -struct-fields

### -field NodeOrdinal

[in] An index of a node within the physical adapter defined by   the <b>EngineOrdinal</b> member that is being reset in a call to <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_resetengine">DxgkDdiResetEngine</a>.

### -field EngineOrdinal

[in] An index that defines the physical adapter in a linked display adapter (LDA) configuration that the node defined by <b>NodeOrdinal</b> belongs to.

### -field LastAbortedFenceId

[out] The fence identifier for the last packet that was aborted in the middle of execution.

## -remarks

For more information, see <a href="/windows-hardware/drivers/display/tdr-changes-in-windows-8">TDR changes in Windows 8</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_resetengine">DxgkDdiResetEngine</a>
