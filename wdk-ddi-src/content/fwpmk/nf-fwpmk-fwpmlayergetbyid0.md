---
UID: NF:fwpmk.FwpmLayerGetById0
tech.root: netvista
title: FwpmLayerGetById0
ms.date: 06/10/2024
targetos: Windows
description: The FwpmLayerGetById0 function retrieves a layer object.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fwpmk.h
req.idl: 
req.include-header: 
req.irql: <= PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: fwpkclnt.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fwpmk.h
api_name:
 - FwpmLayerGetById0
f1_keywords:
 - FwpmLayerGetById0
 - fwpmk/FwpmLayerGetById0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmLayerGetById0
---

## -description

The **FwpmLayerGetById0** function retrieves a layer object.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param id [in]

Identifier of the desired layer. For a list of possible values, see [Run-time Filtering Layer Identifiers](/windows-hardware/drivers/network/run-time-filtering-layer-identifiers) in the WDK documentation for Windows Filtering Platform.

### -param layer [out]

The layer information.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The layer was retrieved successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

The caller must free the returned object by a call to **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**.

The caller needs [FWPM_ACTRL_READ](/windows/desktop/FWP/access-right-identifiers) access to the layer. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**FwpmLayerGetById0** is a specific implementation of **FwpmLayerGetById**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**
- **[FWPM_ACTRL_READ](/windows/desktop/FWP/access-right-identifiers)**
- **[FWPM_LAYER0](/windows/desktop/api/fwpmtypes/ns-fwpmtypes-fwpm_layer0)**
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Error Codes](/windows/desktop/FWP/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
- [Run-time Filtering Layer Identifiers](/windows-hardware/drivers/network/run-time-filtering-layer-identifiers)
