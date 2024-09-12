---
UID: NF:fwpmk.FwpmLayerGetByKey0
tech.root: netvista
title: FwpmLayerGetByKey0
ms.date: 06/10/2024
targetos: Windows
description: The FwpmLayerGetByKey0 function retrieves a layer object.
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
 - FwpmLayerGetByKey0
f1_keywords:
 - FwpmLayerGetByKey0
 - fwpmk/FwpmLayerGetByKey0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmLayerGetByKey0
---

## -description

The **FwpmLayerGetByKey0** function retrieves a layer object.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param key [in]

Unique identifier of the layer. See [Filtering Layer Identifiers](/windows/desktop/FWP/management-filtering-layer-identifiers-) for a list of possible GUID values.

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

**FwpmLayerGetByKey0** is a specific implementation of **FwpmLayerGetByKey**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**
- **[FWPM_ACTRL_READ](/windows/desktop/FWP/access-right-identifiers)**
- [Filtering Layer Identifiers](/windows/desktop/FWP/management-filtering-layer-identifiers-)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
